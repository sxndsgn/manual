<script setup>
import Title from '../components/Title.vue'
import VerticalCard from '~/components/VerticalCard.vue';

import subrayado5 from '~/assets/img/subr_5.svg';


import colorPrimary from '~/assets/img/color-pr.png';
import colorSec from '~/assets/img/color-sec.png';
import colorAccent from '~/assets/img/color-acc.png';
import colorNeutro from '~/assets/img/color-neutral.png';

const route = useRoute();

const colorData = [
  {
    titulo: 'Color primario',
    texto:'El color principal es un tono azul vibrante que aporta modernidad y profundidad en su versión más oscura.',
    foto: colorPrimary,
  },
  {
    titulo: 'Color acento',
    texto:'El amarillo como color acento tiene una función táctica de actuar como llamada de atención.',
    foto: colorAccent,
  },
  {
    titulo: 'Color Secundario',
    texto:'El rosa introduce en la marca dinamismo y emocionalidad, aplicándose en trazos y detalles  para aportar ese carácter rebelde y disruptivo.',
    foto: colorSec,
  },
  {
    titulo: 'Colores neutros',
    texto:'La paleta neutra funciona como base sólida para todas las composiciones y garantiza el funcionamiento de la marca en cualquier soporte.',
    foto: colorNeutro,
  }
];
</script>


<template>
  <div class="pageContent">
    <img src="../assets/img/paint3.png" alt="" class="decoTop">


    <Title texto="Color"  :subrayado="subrayado5"/>
    <div v-for="info in colorData" :key="info.titulo" class="section">
        <VerticalCard :titulo="info.titulo" :texto="info.texto" :foto="info.foto"/>
    </div>

      <img src="../assets/img/paint4.png" alt="" class="decoBottom">

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
      margin-left: 13rem;
      margin-top: -10rem;
    }
    .decoBottom{
      position: absolute;
      z-index: 0;
      pointer-events: none;
      height: 400px;
      margin-left: 70rem;
      bottom: -20em;
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