<script setup>
import Title from '../components/Title.vue'
import Card from '../components/Card.vue'

import subrayado5 from '~/assets/img/subr_5.svg';
import tipoImg from '~/assets/img/Tipografia01.png'
import tipoImg2 from '~/assets/img/Tipografia02.png'
import tipoImg3 from '~/assets/img/Tipografia03.png'
import tipoImg4 from '~/assets/img/Tipografia04.png'

const route = useRoute();

const tipoData = [
  {
    titulo: 'Tipografía principal',
    texto: 'Como tipografía decorativa principal para grandes titulares, utilizamos Movement. Una tipografía escogida por su carácter dinámico y expresivo, que transmite a la perfección la actitud y la energía de la plataforma.',
    foto: tipoImg
  },
  {
    titulo: 'Tipografía secundaria',
    texto: 'Utilizamos Overpass Mono como tipografía principal. Una tipografía monoespaciada que remite al mundo digital. Esta se utiliza en el logotipo y en titulares, aportando estructuración a la marca.',
    foto: tipoImg2
  },
  {
    titulo: 'Tipografía de lectura',
    texto: 'Mientras que las tipografías anteriores reflejan el tono y la personalidad de la marca, Overpass es la tipografía que utilizamos de forma estándar para textos seguidos, garantizando la lectura cómoda sin perder identidad.',
    foto: tipoImg3
  }
];
</script>

<template>
  <div class="pageContent">
    <img src="../assets/img/paint1.svg" alt="" class="decoTop">

    <Title texto="TIPOGRAFÍA"  :subrayado="subrayado5"/>

      <div v-for="info in tipoData" :key="info.titulo" class="section">
        <div class="cardWrapper">
          <Card :titulo="info.titulo" :texto="info.texto"/>
        </div>
        <div class="imageWrapper">
          <img :src="info.foto" alt="Tipografía" class="tipoImage"/>
        </div>
      </div>

      <div class="section sectionComposition">
        <Card titulo="EJEMPLO DE COMPOSICIÓN" />
        <img :src="tipoImg4" alt="Ejemplo de composición" class="tipoImage compositionImage">
      </div>

      <img src="../assets/img/cornerPaint.svg" alt="" class="decoBottom">

  </div>
  
  

</template>

<style scoped lang="scss">
@use '../assets/sass/main';
@use '../assets/sass/partials/variables' as v;



.pageContent {
  position: relative;
    .decoTop{
      position: absolute;
      z-index: -1; // ← detrás de todo
      pointer-events: none;
      height: 280px;
      margin-left: 10rem;
      margin-top: -12rem;
    }
    .decoBottom{
      position: absolute;
      z-index: 0;
      pointer-events: none;
      height: 400px;
      margin-left: 81rem;
      bottom: -10.5rem;
    }
    .sectionRelProp ~ .decoBottom{
      margin-left: 81rem;
      bottom: -7rem;
    }
    .section{
      margin-left: 25rem;
      margin-right: 5rem;
      margin-top: v.$sp-10;
      display: flex;
      gap: 2rem;
      align-items: flex-start;
    }
    .sectionComposition {
      margin-top: 8rem; 
      display: block; 
      .compositionImage {
        margin-top: 0rem;
        width: 40%; 
      }
    }
    .cardWrapper {
      flex: 1;
      min-width: 0;
    }
    .imageWrapper {
      flex: 1;
      min-width: 0;
      margin-top: 2rem; 
    }
    .tipoImage {
      width: 100%;
      height: auto;
      display: block;
    }
}

</style>