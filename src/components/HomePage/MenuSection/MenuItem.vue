<template>
    <div class="flex flex-col justify-center text-darkgray bg-white mx-10 rounded-3xl p-2">
        <img  class="rounded-full mx-auto mt-5 size-60 sm:size-70 object-cover" :src="imgSrc">
        <div class="flex flex-col shadow-2xl m-5 p-5 rounded-2xl">
            <h1 class=" text-center text-lg sm:text-xl underline">{{ name }}</h1>
            <p class="text-[12px] sm:text-[14px] text-center mx-2 italic">{{ description }}</p>
            <h2 class="text-center text-lg sm:text-xl my-2">€{{ price }}</h2>
            <button class="font-bold bg-amber-500 p-4" @click="addToCart"><i class="fa-solid fa-cart-arrow-down"></i> Add to cart</button>
        </div>

    </div>
</template>

<script setup lang="ts">
defineProps<{
    imgSrc: string
    name: string
    description?: string 
    price: number
}>()

const emit = defineEmits(['addToCart'])

const addToCart = () => {
    emit('addToCart')
}

</script>

<style scoped>

</style>