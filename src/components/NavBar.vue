<template>
    <header class="bg-darkgray text-white h-20 w-full flex flex-row items-center">
        <div class="flex h-20 w-full justify-start">
            <img class="py-2 ml-5" src="/src/assets/logo.png">
        </div>

        <div @click="activeDropDown = !activeDropDown"  class="w-full flex flex-row items-center justify-end pr-3">
            <i class="fa-solid fa-bars"></i>

                <div class="flex flex-col relative mr-5">Menu</div>
                <div v-if="activeDropDown"  class="flex flex-col right-0 absolute top-15 bg-black mr-2 p-3 rounded-2xl z-100">    
                    <button>Menu</button>
                    <button>About</button>
                    <button>Contact</button>
                </div>
            </div>


    </header>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const activeDropDown = ref<boolean>(false)

</script>

<style scoped>

</style>