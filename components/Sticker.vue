<script setup>
const props = defineProps({
    textura: String, //hola chicos, para que funcione teneis que meter en textura la ruta de la textura vale?
    alt: {
        type: String,
        default: 'sticker'
    },
    tamano: {
        type: String,
        default: '159px'
    }
})
</script>

<template>
    <div class="sticker-wrapper" :style="{ width: tamano, height: tamano }">
        <img :src="textura" :alt="alt" class="sticker-img">
    </div>
</template>

<style scoped lang="scss">
@use '../assets/sass/main';
@use '../assets/sass/partials/variables' as v;

.sticker-wrapper {
display: flex;
overflow: hidden;
align-items: center;
justify-content: center;
border-radius: v.$radius-6; 
background-color: v.$color-primary-very-light; 
border: v.$border solid v.$color-neutral;
  
  .sticker.img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
  }
}
</style>