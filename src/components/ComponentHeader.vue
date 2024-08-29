<script setup>
import {computed, ref,defineProps} from 'vue'
import Logo from '../assets/logo.svg'


const isActive = ref(false)



</script>
<template>
    
        <header class="w-full shadow">
            <nav class="flex p-4 items-center w-full justify-between bg-white">
                    <div class="flex justify-between w-full lg:w-auto items-center">
                        <span class="">
                           <img src="../assets/logo.svg" alt="">
                        </span>
                        <span class="text-3xl cursor-pointer lg:hidden block">
                            <ion-icon :name="isActive ? 'close' : 'menu'" @click="isActive = !isActive"></ion-icon>
                        </span>
                    </div>
                    
                    <ul 
                    class="lg:flex lg:items-center lg:static absolute left-0 bg-white lg:opacity-100 top-0 w-full h-full lg:w-auto py-4 lg:py-0 transition-all ease-in z-[-1] lg:z-auto" 
                    :class="isActive ? ['top-[70px]','opacity-100']: ['top-[-300px]','opacity-0']" >
                    <li class="mx-6 my-6 lg:my-0 font-semibold"><a  href="#">Home</a></li>
                    <li class="mx-6 my-6 lg:my-0 font-semibold"><a  href="#">About</a></li>
                    <li class="mx-6 my-6 lg:my-0 font-semibold"><a  href="#">Service</a></li>
                    <li class="mx-6 my-6 lg:my-0 font-semibold"><a  href="#">Contact</a></li>
                    <button class="py-2 px-5  mx-4 rounded-full bg-black text-cyan-50 items-center text-sm font-semibold">Get Started</button>

                </ul>
                
            </nav>
            
        </header>
</template>

<style scoped>
</style>