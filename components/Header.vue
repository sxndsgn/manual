<script setup>

</script>

<template>
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

header {
    position: fixed;
    width: 90%;
    z-index: 2000; 
    margin-left: 2.75rem;
    margin-top: 3.375rem;
    .headerContent{
        position: relative;
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: v.$sp-13;
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