
<template>
    <div class="body-container" style="background:#f2f2f2;">
        <header class="h-16 bg-teal-800 drop-shadow-lg">
            <div class="container px-4 md:px-0 h-full mx-auto flex justify-between items-center">
                <div class="flex items-center md:hidden">
                    <button class="text-white text-4xl font-bold opacity-70 hover:opacity-100 duration-300"
                        @click="toggleMenu">
                        &#9776;
                    </button>
                </div>
                <ul 
                    id="menu" 
                    class="fixed top-0 right-0 px-10 py-16 bg-gray-800 z-50 md:relative md:flex md:p-0 md:bg-transparent md:flex-row md:space-x-6"
                    :class="{'hidden': hide, 'w-full': !hide}"
                >
                    <li class="md:hidden z-90 fixed top-4 right-6">
                        <button class="text-right text-white text-4xl" @click="toggleMenu">&times;</button>
                    </li>
                    <li>
                        <NuxtLink to="/" class="text-white opacity-70 hover:opacity-100 duration-300">Home</NuxtLink>
                    </li>
                    <li>
                        <NuxtLink to="/portfolio" class="text-white opacity-70 hover:opacity-100 duration-300">Portfolio</NuxtLink>
                    </li>
                </ul>
            </div>
        </header>
        <Nuxt />
    </div>
    

</template>
<script>
    export default {
        name: 'Default',

        data() {
            return {
                hide: true,

            }
        },
        
        methods: {
            toggleMenu() {
                this.hide = !this.hide;
            }
        }
    }
</script>