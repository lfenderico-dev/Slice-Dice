<template>
    <div class="flex flex-col gap-5 rounded-2xl shadow-2xl shadow-darkgray mx-4 my-4">
        <img class="mx-auto w-80 h-60 lg:w-90 lg:h-70 xl:w-100 xl:h-80 object-cover rounded-2xl mt-5" :src="imgSrc">

        <div class="flex flex-row gap-1 justify-center text-xl lg:text-2xl xl:text-3xl text-amber-500">
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
            <i class="fa-solid fa-star"></i>
        </div>

        <h1 class="text-2xl lg:text-3xl xl:text-4xl text-center font-bold">{{ reviewHeading }}</h1>
        <p class="text-center text-[10px] lg:text-[12px] xl:text-[14px] px-4 italic">{{ review }}</p>

        <div class="flex flex-row justify-center text-xl lg:text-2xl xl:text-3xl items-center mb-5">
            <i class="fa-solid fa-check-double"></i>
            <h1 class="underline p-3">{{ name }}</h1>
        </div>

    </div>
</template>

<script setup lang="ts">
defineProps<{
    imgSrc: string
    reviewHeading?: string
    review: string
    name: string
}>()
</script>

<style scoped>

</style>