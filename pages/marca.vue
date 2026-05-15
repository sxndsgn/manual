<script setup>
import Title from '../components/Title.vue'
import Card from '../components/Card.vue'
import VerticalCard from '~/components/VerticalCard.vue';

import subrayado from '~/assets/img/subr_1.svg';
import subrayado2 from '~/assets/img/subr_2.svg';
import subrayado3 from '~/assets/img/subr_3.svg';
import subrayado4 from '~/assets/img/subr_4.svg';
import subrayado5 from '~/assets/img/subr_5.svg';
import subrayado6 from '~/assets/img/subr_6.svg';
import subrayado7 from '~/assets/img/subr_7.svg';
import logoImg from '~/assets/img/logo.svg'
import relProp from '~/assets/img/props.svg'
import vColor from '~/assets/img/vColor.svg'
import vMono from '~/assets/img/mono.svg'
import vImg from '~/assets/img/vImage.svg'
import vProh from '~/assets/img/forbidden.svg'

const route = useRoute();
const activeSection = computed(() => route.query.section || 'logotipo');

const logoData = [
  {
    titulo: 'Logotipo',
    foto: logoImg,
    texto: 'El logotipo de la marca esta compuesto por la tipografía Overpass Mono y un cuadrado vacío con borde que representa una pegatina en blanco para que cada artista personalice esta con su esencia.'
  },
  {
    titulo: 'Variabilidad',
    texto: 'En Bandcamp cada artista tiene personalidad, y esta se extiende a Bandcamp, pudiendo adoptar el isotipo el patrón creado por cada uno de los artistas de la plataforma.'
  }
];

const relacionesProporcionalesData = [
  {
    titulo: 'Relaciones proporcionales',
    foto: relProp,
    texto: 'La marca se construye a partir de la medida de la letra “m” minúscula del logotipo.  A partir de esta medida, se marcan el espaciado entre las partes (0.5x) y el área de respeto (1x).'
  }
];

const versionesData = [
  {
    titulo: 'Versiones monocromáticas',
    foto: vMono,
  },
  {
    titulo: 'Versiones a color',
    foto: vColor,
  },
  {
    titulo: 'Sobre imagen',
    foto: vImg,
  },
  {
    titulo: 'Versiones prohibidas',
    foto: vProh,
  }
];

</script>


<template>
  <div class="pageContent">
    <img src="../assets/img/paint1.svg" alt="" class="decoTop">

    <Title texto="Marca gráfica"  :subrayado="subrayado5"/>

      <div v-if="activeSection === 'logotipo'" class="section">
        <Card v-for="info in logoData" :key="info.titulo" :titulo="info.titulo" :texto="info.texto" :foto="info.foto"/>
      </div>

      <div v-else-if="activeSection === 'relacionesProporcionales'" class="section sectionRelProp">
        <VerticalCard v-for="info in relacionesProporcionalesData" :key="info.titulo" :titulo="info.titulo" :texto="info.texto" :foto="info.foto"/>
      </div>

      <div v-else-if="activeSection === 'versiones'" class="section">
        <VerticalCard v-for="info in versionesData" :key="info.titulo" :titulo="info.titulo" :texto="info.texto" :foto="info.foto"/>
      </div>

      <img src="../assets/img/cornerPaint.svg" alt="" class="decoBottom">

  </div>
  

</template>

<style lang="scss">
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
      margin-right: 15rem;
      margin-top: v.$sp-10;
    }
}

</style>