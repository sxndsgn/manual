<script setup>
import { computed } from 'vue'
import { useRoute } from '#app' 
import Header from './components/Header.vue' 
import Sidebar from './components/Sidebar.vue' 

const route = useRoute()

const showSidebar = computed(() => {
 
  return route.path === '/aplicaciones' || route.path === '/marca'
})
</script>

<template>
    <div>
        <Header />
        <Sidebar v-if="showSidebar" />
        <NuxtPage />
    </div>
</template>

<style> 
</style>
