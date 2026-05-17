<script setup>
import Title from '../components/Title.vue'
import VerticalCard from '~/components/VerticalCard.vue';
import subrayado5 from '~/assets/img/subr_5.svg';
import texturas from '~/assets/img/foto-texturas.png';
import producto from '~/assets/img/foto-producto.png';
import fotografia from '~/assets/img/foto.png';
const route = useRoute();

const fotoData = [
  {
    titulo: 'Texturas',
    texto:'A menudo se recurre a texturas similares al hormigón, con imperfecciones, grietas o rugosidad para reflejar el lado más humano de la plataforma.',
    foto: texturas,
  },
  {
    titulo: 'Producto',
    texto:'Para comunicaciones específicas de la marca se utilizan fotografías de productos relacionados con la música en los que se ven las pegatinas pegadas.',
    foto: producto,
  },
  {
    titulo: 'Fotografía',
    texto:'En los casos en los que utilicemos fotografías propias, estas tendrán un tono crudo, monocromático en blanco y negro con mucho contraste. ',
    foto: fotografia,
  }
];
</script>


<template>
  <div class="pageContent">
    <img src="../assets/img/paint1.svg" alt="" class="decoTop">

    <Title texto="Estilo Fotográfico"  :subrayado="subrayado5"/>
    <div v-for="info in fotoData" :key="info.titulo" class="section">
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