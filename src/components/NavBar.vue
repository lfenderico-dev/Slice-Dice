<template>
    <header class="bg-darkgray text-white h-20 w-full flex flex-row items-center">
        <div class="flex h-20 w-full">
            <img class="py-2 ml-5" src="/src/assets/logo.png">
        </div>

        <div @click="activeDropDown = !activeDropDown" class="relative w-full justify-end flex mr-4">
            <div class="flex flex-row items-center mr-4">
                <i class="fa-solid fa-bars"></i>
                <div>Menu</div>
            </div>

            <div v-if="activeDropDown" class="backdrop-blur w-[100vh] h-[100vh] z-50 fixed inset-0"></div>
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