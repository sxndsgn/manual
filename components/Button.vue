<script setup>
 const props = defineProps({
        texto: String,
        clase: String,
        ir: String
 })
 const irAMarca = () => {
    if (props.ir) {
        navigateTo(props.ir)
    }
}
</script>

<template>
    <button :class="clase" @click="irAMarca">{{ texto }}</button>
</template>
<style scoped lang="scss">
@use '../assets/sass/main';
@use '../assets/sass/partials/variables' as v;

button{
    font-family: overpass, sans-serif;
    font-size: 1rem;
    font-weight: 600;
    line-height: 1.5;
    letter-spacing: -0.01;
    max-width: 650px;
    gap: v.$sp-02;
    padding: v.$sp-03 v.$sp-04;
    border-radius: v.$radius-2;
    width: fit-content; 
}
.p-btn {
        background-color:v.$color-primary-very-dark;
        color: v.$color-primary-medium-light;
        &:hover{
            background-color: v.$color-primary;
            color: v.$color-accent;
        }
        &:focus{
            background-color: transparent;
            color: v.$color-primary-very-dark;
            border: v.$border-2 solid v.$color-primary-medium-light;
        }
        &:disabled{
            background-color: v.$color-primary-very-light;
            color: v.$color-primary-light;
       }
       }
.s-btn {
        background-color:v.$color-secondary-medium-light;
        color: v.$color-primary-very-dark;
        &:hover{
            background-color: v.$color-primary-very-dark;
            color: v.$color-secondary;
        }
        &:focus{
            background-color: transparent;
            color: v.$color-primary-very-dark;
            border: v.$border-2 solid v.$color-secondary-medium-light;
        }
        &:disabled{
            background-color: v.$color-secondary-light;
            color: v.$color-secondary-medium-light;
        }
    }
    
</style>