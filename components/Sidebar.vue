<script setup>
const route = useRoute()
const isActive = (section) => route.query.section === section
</script>

<template>
  <nav class="navbar">
    <ul class="navbar-list">
      <li>
        <NuxtLink to="/marca?section=logotipo">Marca Gráfica</NuxtLink>
        <ul class="sub-list">
          <li><NuxtLink to="/marca?section=logotipo" >Logotipo</NuxtLink></li>
          <li><NuxtLink to="/marca?section=relacionesProporcionales">Relaciones proporcionales</NuxtLink></li>
          <li><NuxtLink to="/marca?section=versiones">Versiones</NuxtLink></li>
        </ul>
      </li>
      <li><NuxtLink to="/tipografia">Tipografía</NuxtLink></li>
      <li><NuxtLink to="/color">Color</NuxtLink></li>
      <li><NuxtLink to="/fotografia">Estilo Fotográfico</NuxtLink></li>
      <li><NuxtLink to="/elementos">Elementos Gráficos</NuxtLink></li>
    </ul>
  </nav>
</template>

<style scoped lang="scss">
@use '../assets/sass/main';
@use '../assets/sass/partials/variables' as v;

.navbar {
  background-image: url('../assets/img/FondoNavbarSF.png');
  background-size: 100% 100%; 
  background-position: left top; 
  background-repeat: no-repeat; 
  padding: 40px 20px; 
  display: flex;
  flex-direction: column; 
  justify-content: flex-start; 
  align-items: flex-start; 
  position: fixed; 
  left: 0; 
  top: 0; 
  height: 100vh; 
  width: 350px; 
  z-index: 1000; 

  .navbar-list {
    display: flex;
    flex-direction: column; 
    gap: 15px; 
    list-style: none;
    margin-left: 45px;
    margin-top: 125px; 
    padding: 0;
    width: 100%; 

    li {
      width: 100%; 
      a {
        font-family: Overpass, sans-serif;
        font-size: 1rem;
        font-weight: 700;
        text-decoration: none;
        color: v.$color-primary;
        transition: color 0.3s ease;
        

        &:hover, &.router-link-active {
          color: v.$color-secondary;
        }
      }

      .sub-list {
        list-style: none;
        padding-left: 20px;
        margin-top: 10px;
        display: flex;
        flex-direction: column;
        gap: 8px;

        a {
          font-size: 0.85rem;
          font-weight: 500;
          text-transform: none;
        }
      }
    }
  }
}
</style>