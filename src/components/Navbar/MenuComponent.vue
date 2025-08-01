<template>
    <div class="fade-in-right bg-darkgray shadow-2xl shadow-black w-full h-fit p-4 rounded-2xl absolute top-8 flex flex-col z-100 gap-y-2 sm:text-lg lg:text-2xl">
        <button @click="scrollToAbout">About</button>
        <button @click="scrollToMenu">Menu</button>
        <button @click="scrollToContacts">Contact us</button>
        <button @click="scrollToInfo">Info</button>
    </div>
</template>

<script setup lang="ts">
const scrollToAbout = ()=>{
  document.getElementById('about')?.scrollIntoView({behavior: 'smooth'})
}

const scrollToMenu = ()=>{
  document.getElementById('menu')?.scrollIntoView({behavior: 'smooth'})
}

const scrollToContacts = ()=>{
  document.getElementById('contacts')?.scrollIntoView({behavior: 'smooth'})
}

const scrollToInfo = ()=>{
  document.getElementById('info')?.scrollIntoView({behavior: 'smooth'})
}
</script>

<style scoped>
@keyframes fadeInRight {
  from {
    opacity: 0;
    transform: translateX(100%);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}
.fade-in-right {
  animation: fadeInRight 0.3s cubic-bezier(.4,0,.2,1);
}

</style>