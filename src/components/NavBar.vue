<template>
    <header class="bg-darkgray text-white h-20 sm:h-30 lg:h-40 2xl:h-50 w-full flex flex-row items-center">
        <div class="flex h-20 sm:h-30 lg:h-40 2xl:h-50 w-full xl:ml-8">
            <img loading="lazy"  class="py-2 ml-5 lg:pt-8" src="/src/assets/logo.png">
        </div>

        <div @click="activeDropDown = !activeDropDown" class="relative w-full justify-end flex mr-4 xl:mr-8 sm:text-lg lg:text-2xl xl:text-3xl">
            <div class="flex flex-row items-center mr-4">
                <i class="fa-solid fa-bars"></i>
                <div>Menu</div>
            </div>

            <div v-if="activeDropDown" class="backdrop-blur w-full h-full z-50 fixed inset-0"></div>
            <MenuComponent v-if="activeDropDown"/>
        </div>
        

    </header>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import MenuComponent from './Navbar/MenuComponent.vue';

const activeDropDown = ref<boolean>(false)

</script>

<style scoped>

</style>