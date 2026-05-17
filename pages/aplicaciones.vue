<script setup>
import aplicacion1 from '../assets/img/aplicacion1.png'
import aplicacion2 from '../assets/img/aplicacion2.png' 
import aplicacion3 from '../assets/img/aplicacion3.png' 
import aplicacion4 from '../assets/img/aplicacion4.png' 
import aplicacion5 from '../assets/img/aplicacion5.png'  

const aplicaciones = [
  { id: 1, src: aplicacion1, alt: 'Aplicación 1' },
  { id: 2, src: aplicacion2, alt: 'Aplicación 2' },
  { id: 3, src: aplicacion3, alt: 'Aplicación 3' },
  { id: 4, src: aplicacion4, alt: 'Aplicación 4' },
  { id: 5, src: aplicacion5, alt: 'Aplicación 5' },
]
</script>

<template>
  <main class="aplicaciones">
    <img
      v-for="app in aplicaciones"
      :key="app.id"
      :src="app.src"
      :alt="app.alt"
    >
  </main>
</template>

<style scoped lang="scss">
@use '../assets/sass/main';
@use '../assets/sass/partials/variables' as v;

.aplicaciones{
  margin: -7.9rem;
}
img{
  width: 100%;
  height: auto;
}
</style>