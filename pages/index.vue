
<script setup>
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
        <img src="../assets/img/rizo-hero.png" alt="rallajo" class="rallajo2">
        <img src="../assets/img/rallajo-hero2.png" alt="rallajo" class="rallajo3">
      
      <Sticker textura="" tamano="159px" alt="Sticker-Hero1" />
      <Sticker textura="" tamano="159px" alt="Sticker-Hero2" />

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
</style>