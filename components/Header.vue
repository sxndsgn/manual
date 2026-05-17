<script setup>

</script>

<template>
    <div class="headerGradient">
        
    </div>
    <header>
        <div class="headerContent">
            <div class="headerLeft">
                <NuxtLink to="/">
                    <img src="/public/logo.svg" alt="">
                </NuxtLink>  
            </div>

            <nav class="headerRight">
                <ul>
                    <li>
                        <NuxtLink to="/marca">Nuestra marca</NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/aplicaciones">Aplicaciones</NuxtLink></li>
                </ul>
            </nav>
        </div>
        
    </header>
</template>

<style scoped lang="scss">
@use '../assets/sass/main';
@use '../assets/sass/partials/variables' as v;

.headerGradient{
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 150px; 
     background: linear-gradient(
        to bottom,
        v.$color-neutral 20%,
        transparent 100%
    );
    z-index: 50; 
    pointer-events: none;
}

header {
    margin: -4rem;
    padding: 0;
    position: fixed;
    width: 100%;
    z-index: 2000; 
   
    
    .headerContent{
        margin: 4rem;
        margin-bottom: 0;
        width: 90%;
        position: relative;
        display: flex;
        justify-content: space-between;
        align-items: center;
        .headerLeft {
            img {
                width: 150px;
            }
        }

        .headerRight {
            ul {
                display: flex;
                gap: v.$sp-13;

                li {
                    list-style: none;
                    a {
                        font-family: Overpass, sans-serif;
                        font-size: 1rem;
                        font-weight: 700;
                        text-transform: uppercase;
                        text-decoration: none;
                        color: v.$color-primary;
                        transition: color 0.3s ease;

                        &:hover {
                        color: v.$color-secondary;
                        }
                    }
                }
            }
        }
    }
    
}
</style>