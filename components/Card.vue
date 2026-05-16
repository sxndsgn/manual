<script setup>
defineProps({
  titulo: String,
  foto: String,
  texto: String
})
</script>

<template>
  <div class="card">
    <div class="cardLeft">
        <div class="cTitleSec">
            <img src="~/assets/img/dot.svg" alt="" class="dot">
            <h1 class="cardTitle">{{ titulo }}</h1>
        </div>
        <p class="cardText">{{ texto }}</p>
    </div>
    

    <div class="cardRight" v-if="foto">

        <img :src="`${foto}`" alt="" class="foto">
    </div>
  </div>
</template>

<style lang="scss">
@use '../assets/sass/main';
@use '../assets/sass/partials/variables' as v;

.card{
    margin-top: 2rem;
    display: flex;
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
        width: 70%;
        font-family: Overpass, sans-serif;
        font-size: 1rem;
        line-height: 1.5;
        margin-left: 2rem;
    }

    .cardRight {
        display: flex;
        flex-direction: row;
        width: 100%;
        .foto {
            width: 100%;
            height: auto;
        }
    }
    
}
</style>

