<script setup>
import { computed } from 'vue'
import { useRoute } from '#app' 
import Header from './components/Header.vue' 
import Sidebar from './components/Sidebar.vue' 

const route = useRoute()

const showSidebar = computed(() => {
  return route.path === '/marca' || route.path === '/tipografia'
})
</script>

<template>
    <div>
        <Header />
        <Sidebar v-if="showSidebar" />
        <div class="mainContent">
            <NuxtPage />
        </div>
        
    </div>
</template>

<style lang="scss"> 
@use './assets/sass/main';
@use './assets/sass/partials/variables' as v;
html, body {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}
.mainContent {
    padding-top: 4rem;
    padding-bottom: 3rem;
    
}
</style>
