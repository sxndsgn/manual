<script setup>
import Title from '../components/Title.vue'
import VerticalCard from '~/components/VerticalCard.vue';
import subrayado5 from '~/assets/img/subr_5.svg';
import patrones from '~/assets/img/patrones.png';
import pegatinas from '~/assets/img/pegatinas.png';
import trazos from '~/assets/img/trazos.png';

const route = useRoute();

const elementosData = [
  {
    titulo: 'Patrones',
    texto:'Dentro del sistema hay un conjunto de texturas gráficas con colores vibrantes que se utilizan para rellenar formas geométricas. Estos patrones son creados por los propios artistas a partir de los colores y pinceles que forman parte de la identidad de Bandcamp.',
    foto: patrones,
  },
  {
    titulo: 'Pegatinas',
    texto:'Como principal elemento representativo de la marca se utilizan las pegatinas que contienen los patrones de artistas. Estas pegatinas son representativas de la relación de cada individuo con los artistas de la plataforma, pues en función de qué tipo de productos adquieran o el tiempo que lleven escuchando al artista, su pegatina tendrá una forma u otra.',
    foto: pegatinas,
  },
  {
    titulo: 'Trazos',
    texto:'Las líneas, garabatos y subrayados de aspecto manual representan la intervención humana y la energía de Bandcamp. Rompen con los estándares de digitalización, ayudando a humanizar la plataforma.',
    foto: trazos,
  }
];
</script>


<template>
  <div class="pageContent">
    <img src="../assets/img/paint1.svg" alt="" class="decoTop">

    <Title texto="Elementos Gráficos"  :subrayado="subrayado5"/>

    <div v-for="info in elementosData" :key="info.titulo" class="section">
        <VerticalCard :titulo="info.titulo" :texto="info.texto" :foto="info.foto"/>
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
      z-index: -1; 
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
      margin-left: 81.5rem;
      bottom: -12em;
    }
    .sectionRelProp ~ .decoBottom{
      margin-left: 81rem;
      bottom: -7rem;
    }
    .section{
      margin-left: 25rem;
      margin-right: 15rem;
      margin-top: v.$sp-10;
    }
}

</style>