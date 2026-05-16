<script setup>
import imgSubrayado from '../assets/img/subrayado.png';
import imgSubrayadoAmar from '../assets/img/subrayado-amar.svg';
import textura1 from '../assets/img/texturas/7.png';
import textura8 from '../assets/img/texturas/8.png';
const valores = [
  {
    titulo: 'Misión',
    texto: 'Buscamos conectar a la comunidad musical a través de una plataforma transparente y humana que elimina los intermediarios. Existimos para dar a los artistas el control total sobre su obra y a los oyentes una experiencia de descubrimiento auténtico y emocionante.'
  },
  {
    titulo: 'Visión',
    texto: 'Nuestro objetivo es convertirnos en el referente global de la cultura musical independiente, siendo el espacio en el que la música se consume, se vive y se interviene. Así, aspiramos a ser una plataforma en constante movimiento que da espacio a cualquier creador.'
  },
  {
    titulo: 'Filosofía',
    texto: 'Somos una plataforma viva, un escenario de acción e intervención constante para quienes forman parte de ella. Así, la plataforma deja de ser un espacio de consumo pasivo para ser un espacio en el que la participación y el movimiento constante importan.'
  }
];

const atributos = [
  { titulo: 'Transparente', 
    texto: 'Sabemos lo que vale tu música y te lo dejamos claros, sin trampas ni intermediarios.' 
  },
  { titulo: 'Auténtica', 
    texto: 'Nuestra relación es genuina y sin pretensiones. Creemos en la música y las conexiones reales.' 
  },
  { titulo: 'Interactiva', 
    texto: 'Con nosotros no solo escuchas, también participas, comentas, compartes, descubres y apoyas.' 
  },
  { titulo: 'Justa', 
    texto: 'Cada artista tiene su oportunidad, y cada compra es un apoyo directo.' 
  },
  { titulo: 'Creativa', 
    texto: 'Optamos por la originalidad, lo diferente y lo que no se encuentra en las radios.' 
  }
];

</script>

<template>
  <main class="home">
    <section class="hero">
      <div class="hero background">
        <img src="../assets/img/fondo-hero.png" alt="hero background" class="hero-background-img">
        
        <img src="../assets/img/rallajo-hero1.png" alt="rallajo" class="rallajo1">
        <img src="../assets/img/rizo-hero.png" alt="rallajo" class="rallajo3">
        <img src="../assets/img/rallajo-hero2.png" alt="rallajo" class="rallajo2">
      
      <Sticker :textura="textura1" tamano="159px" alt="Sticker-Hero1" class="sticker1" />
      <Sticker :textura="textura8" tamano="159px" alt="Sticker-Hero2" class="sticker2" />

      <img src="../assets/img/cascos.png" alt="" class="cascos">
    </div>
      <div class="hero-texto">
        <h1>Tu música se pega</h1>
        <h5 class="h5-ligth">La plataforma más viva</h5>
        <Button texto="Ver manual" clase="s-btn" ir="/marca"/>
      </div>
    </section>

     <section class="valores">
      <img src="../assets/img/RotoAmarillo.png" alt="valores background" class="valores-background">
      <div class="valores-items">
        <article v-for="(item, index) in valores" :key="index" class="item">
          <h4 class="h4-mono">{{ item.titulo }}</h4>
          <img src="../assets/img/subrayado.png" alt="" class="subrayaado">
          <p class="p">{{ item.texto }}</p>
        </article>
      </div>
    </section>

    <section class="atributos">
      <article v-for="(atributo, index) in atributos" :key="index" class="atributo-item">
        <h4 class="h4-mono">{{ atributo.titulo }}</h4>
        <img src="../assets/img/subrayado-amar.svg" alt="" class="subrayaado">
        <p class="p">{{ atributo.texto }}</p>
      </article>
    </section>
  </main>
</template>

<style scoped lang="scss">
@use '../assets/sass/main';
@use '../assets/sass/partials/variables' as v;

.hero{
 .hero-background-img{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 900px;
    object-fit: cover;
    z-index: -1;
  }
  .rallajo1{
    position: absolute;
    top: 20%;
    height: 448.62px;
    width: auto;
    left: 0;
    z-index: 1;
 
  }
  .rallajo2{
    position: absolute;
    top: 30%;
    height: 483px;
    width: auto;
    right: 25%;
    z-index: 1;
  }
  .rallajo3{
    position: absolute;
    top: -30%;
    height: 1144.32px;
    width: auto;
    left: 70%;
    z-index: 1;
  }
  .sticker1 {
  position: absolute;
  top: 85%;
  left: 1%;
  z-index: 10;
  rotate: 16.2deg;
  animation: popIn 0.5s ease forwards;
}

.sticker2 {
  position: absolute;
  top: 30%;
  left: 92%;
  z-index: 10;
  rotate: 16.2deg;
  animation: popIn 0.5s ease forwards;
}

@keyframes popIn {
  0% {
    opacity: 0;
    transform: scale(0);
  }
  70% {
    transform: scale(1.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}
  .cascos{
    position: absolute;
    top: 10%;
    height: 697.4px;
    left: 50%;
    z-index: 5;
  }
  .hero-texto{
    margin-top: 0%;
    margin-left: 10%;
    z-index: 10;
    display: flex;
    flex-direction: column;
    align-items: left;
    width: 40%;
    margin-top: 8%;
    h1{
      font-family: movement, sans-serif;
      font-size: 5.6rem;
      letter-spacing: -0.01em;
      max-width: 650px;
      font-weight: bold;
      text-transform: uppercase;
      color:v.$color-primary;
      line-height: 100%;
      margin: 0%;
    }
    h5{
      font-family: overpass Mono, sans-serif;
      font-size: 1.777rem;
      line-height: 1.05;
      letter-spacing: -0.01em;
      max-width: 650px;
      margin: 0%;
      padding-top: 1rem;
      padding-bottom: 1.25rem;
      font-weight: 400;
      width: 50%;

    }
  }
}
.valores{
  position: relative;
  margin-top: 23rem;
      .valores-background{
        position: absolute;
        left: 50%;
        margin-top: -9rem;
        transform: translateX(-50%);
        width: 100vw;  
        height: auto;
        object-fit: cover;
        z-index: -1;
        }
        .valores-items {
      display: flex;
      justify-content: space-between;
      padding: 0 10%;
      align-items: flex-start;
      gap: 2rem;
      
      .item {
        width: 30%;
        padding-left: 1.5rem;
        margin-top: 12%;

        &:first-child {
          padding-left: 0;
        }

        &:not(:first-child) {
          border-left: 2px solid v.$color-primary;
        }

        .h4-mono {
          font-family: overpass mono, monospace;
          font-size: 2.36rem;
          line-height: 1;
          letter-spacing: -0.01em;
          text-transform: uppercase;
          color: v.$color-primary;
          margin: 0;
        }

        .subrayaado {
          width: 55%;
          margin-top: -0.4rem;
          display: block;
        }

        .p {
          font-family: overpass, sans-serif;
          font-size: 1rem;
          line-height: 1.5;
          letter-spacing: -0.01em;
          margin-top: 1.5rem;
        }
      }
    }
  }
.atributos {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    padding: 4rem 10%;
    gap: 3rem 5rem;
    margin-top: 15rem;

    .atributo-item {
      grid-column: span 2;

      &:nth-child(4) {
        grid-column: 2 / span 2;
      }

      &:nth-child(5) {
        grid-column: 4 / span 2;
      }

      .h4-mono {
        font-family: overpass mono, monospace;
        font-size: 2.36rem;
        line-height: 1;
        letter-spacing: -0.01em;
        text-transform: uppercase;
        color: v.$color-primary;
        font-weight: 700;
        margin: 0;
      }

      .subrayaado {
        width: 55%;
        margin-top: -0.4rem;
        display: block;
      }

      .p {
        font-family: overpass, sans-serif;
        font-size: 1rem;
        line-height: 1.5;
        letter-spacing: -0.01em;
        margin-top: 1rem;
      }
    }
  }
</style>