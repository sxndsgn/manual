<script setup>
defineProps({
  titulo: String,
  foto: String,
  texto: String
})
</script>

<template>
  <div class="vCard">
    <div class="cTitleSec">
        <img src="~/assets/img/dot.svg" alt="" class="dot">
        <h1 class="cardTitle">{{ titulo }}</h1>
    </div>
    <p class="cardText">{{ texto }}</p>
    <img :src="`${foto}`" alt="" class="foto">
  </div>
</template>

<style lang="scss">
@use '../assets/sass/main';
@use '../assets/sass/partials/variables' as v;

.vCard{
    width: 70%;
    display: flex;
    flex-direction: column;
    margin-top: 2rem;
    .cTitleSec {
        display: flex;
        align-items: center;
        gap: 1rem;
        margin-bottom: 0;
        .dot{
            width: 1rem;
            margin-bottom: -.5rem;
        }
        .cardTitle{
            margin-bottom: 0;
            color: v.$color-primary;
            font-family: Overpass mono, monospace;
            font-size: 1.333rem;
            text-transform: uppercase;
        }
    }

    p{
        margin-top: 0;
        font-family: Overpass, sans-serif;
        font-size: 1rem;
        line-height: 1.5;
        margin-left: 2rem;
    }
    .foto{
        margin-left: 2rem;
        margin-top: .5rem;
        
    }
}
</style>

