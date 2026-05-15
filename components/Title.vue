<script setup>
 const props = defineProps({
        texto: String,
        subrayado: String
 })
</script>

<template>

    <div class="sectionTitle">
        <h1 class="title">{{ texto }}</h1>
        <img :src="`${subrayado}`" alt="" class="subr">
    </div>
    
</template>

<style scoped lang="scss">
@use '../assets/sass/main';
@use '../assets/sass/partials/variables' as v;

.sectionTitle {
    margin-left: 25rem;
    h1 {
    color: v.$color-primary;
    font-family: Overpass mono, monospace;
    font-size: 3.158rem;
    font-weight: 700;
    text-transform: uppercase;
    }
    .subr {
        margin-top: -2.5rem;
        width: 50%;
    }
    
}

</style>