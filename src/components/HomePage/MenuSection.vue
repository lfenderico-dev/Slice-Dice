<template>
    <div id="menu"  class="h-fit bg-darkgray pb-15">
        <h1 class="text-white text-2xl sm:text-3xl lg:text-4xl xl:text-5xl 2xl:text-6xl font-bold text-center pt-8">Menu</h1>
        <hr class="mx-auto w-10 xl:w-15 h-2 bg-amber-500 border-0 rounded-sm">

        <div class="flex flex-col lg:flex-row py-10 text-white text-lg sm:text-xl xl:text-2xl 2xl:text-3xl gap-5">
            <button @click="category = 'pizza'"  :class="['font-bold mx-auto w-fit shadow-black shadow-2xl px-25 py-3 transition active:scale-120 active:-translate-y-4', category == 'pizza' || category == null ? 'bg-amber-500':'bg-transparent']">Pizza</button>
            <button @click="category = 'appetizers'"  :class="['font-bold mx-auto w-fit shadow-black shadow-2xl px-25 py-3 transition active:scale-120 active:-translate-y-4', category == 'appetizers' ? 'bg-amber-500':'bg-transparent']">Appetizer</button>
            <button @click="category = 'drinks'"  :class="['font-bold mx-auto w-fit shadow-black shadow-2xl px-25 py-3 transition active:scale-120 active:-translate-y-4', category == 'drinks' ? 'bg-amber-500':'bg-transparent']">Drinks</button>
        </div>

        <!-- Pizzas div -->
        <div v-if="category == 'pizza' || category == null"   class="grid grid-cols-1 lg:grid-cols-2 xl:grid-cols-3 2xl:grid-cols-4 xl:gap-6 gap-10">
            <MenuItem v-for="pizza in pizzas" :name="pizza.name" :description="pizza.description" :img-src="pizza.imgSrc" :price="pizza.price" @addToCart="handleCart"/>
        </div>

        <!-- Appetizers div -->
        <div v-if="category == 'appetizers'" class="grid grid-cols-1 lg:grid-cols-2 xl:grid-cols-3 xl:gap-6 gap-10">
            <MenuItem v-for="appetizer in appetizers" :name="appetizer.name" :description="appetizer.description" :img-src="appetizer.imgSrc" :price="appetizer.price" @addToCart="handleCart"/>
        </div>

        <!-- Drinks div -->
        <div v-if="category == 'drinks'" class="grid grid-cols-1 lg:grid-cols-2 xl:grid-cols-3 xl:gap-6 gap-10">
            <MenuItem v-for="drink in drinks" :name="drink.name" :img-src="drink.imgSrc" :price="drink.price" @addToCart="handleCart"/>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const category = ref<string | null>(null)


import MenuItem from './MenuSection/MenuItem.vue';

import margeritaImg from '/src/assets/images/pizzas/margherita.jpg'
import marinaraImg from '/src/assets/images/pizzas/marinara.png'
import quattrostagioniImg from '/src/assets/images/pizzas/4stagioni.png'
import bufalinaImg from '/src/assets/images/pizzas/bufalina.jpg'
import diavolaImg from '/src/assets/images/pizzas/diavola.jpg'
import ortolanaImg from '/src/assets/images/pizzas/ortolana.jpg'
import montanaraImg from '/src/assets/images/pizzas/montanara.jpg'

const pizzas = [
    {
        name: 'Margherita',
        imgSrc: margeritaImg,
        description: 'San Marzano tomato base, fresh mozzarella fior di latte, fresh basil leaves and a drizzle of extra virgin olive oil',
        price: 6.50
    },
    {
        name: 'Marinara',
        imgSrc: marinaraImg,
        description: 'Tomato sauce flavored with fresh garlic, Sicilian oregano and generous seasoning of extra virgin olive oil',
        price: 5.00
    },
    {
        name: 'Quattro Stagioni',
        imgSrc: quattrostagioniImg,
        description: 'Tomato, mozzarella fior di latte, sweet cooked ham, fresh champignon mushrooms, artichokes in oil and Taggiasca black olives',
        price: 8.50
    },
    {
        name: 'Bufalina',
        imgSrc: bufalinaImg,
        description: 'San Marzano DOP tomato, premium Campanian buffalo mozzarella, fresh basil and Apulian extra virgin olive oil',
        price: 9.00
    },
    {
        name: 'Diavola',
        imgSrc: diavolaImg,
        description: 'Spicy tomato base, stringy mozzarella and abundant thinly sliced Calabrian spicy salami',
        price: 7.50
    },
    {
        name: 'Ortolana',
        imgSrc: ortolanaImg,
        description: 'Light tomato, mozzarella, grilled zucchini, diced eggplant, colorful bell peppers and cherry tomatoes',
        price: 8.00
    },
    {
        name: 'Montanara',
        imgSrc: montanaraImg,
        description: 'Rustic tomato, mozzarella, sautéed porcini mushrooms, crumbled mountain sausage and fresh rosemary sprigs',
        price: 9.50
    }
]

import bruschettaImg from '/src/assets/images/appetizers/bruschette.jpg'
import salumiImg from '/src/assets/images/appetizers/salumi.jpg'
import capreseImg from '/src/assets/images/appetizers/caprese.jpg'
import antipastoMareImg from '/src/assets/images/appetizers/antipastoDiMare.png'
import suppliImg from '/src/assets/images/appetizers/suppli.png'
import frittatinaImg from '/src/assets/images/appetizers/frittatina.png'

const appetizers = [
    {
        name: 'Bruschetta',
        imgSrc: bruschettaImg,
        description: 'Toasted Apulian bread rubbed with fresh garlic, diced ripe tomatoes, fragrant basil and extra virgin olive oil',
        price: 4.50
    },
    {
        name: 'Salumi',
        imgSrc: salumiImg,
        description: 'Selection of artisanal cured meats: Parma prosciutto, spicy salami, aged coppa, served with warm focaccia and pickled vegetables',
        price: 10.00
    },
    {
        name: 'Caprese',
        imgSrc: capreseImg,
        description: 'Campanian buffalo mozzarella DOP, ripe San Marzano tomatoes, fresh basil and a drizzle of Apulian extra virgin olive oil',
        price: 8.50
    },
    {
        name: 'Antipasto di mare',
        imgSrc: antipastoMareImg,
        description: 'Marinated octopus with celery and olives, pink shrimp, gratinated mussels, lemon-marinated anchovies and creamy baccalà',
        price: 14.00
    },
    {
        name: 'Suppli',
        imgSrc: suppliImg,
        description: 'Roman rice croquettes with tomato stuffed with stringy mozzarella, breaded and fried to golden perfection',
        price: 5.00
    },
    {
        name: 'Frittatina',
        imgSrc: frittatinaImg,
        description: 'Traditional Neapolitan fried pasta omelet with spaghetti, eggs, pecorino cheese, black pepper and fresh herbs',
        price: 4.50
    }
]

import waterImg from '/src/assets/images/drinks/water.png'
import beerImg from '/src/assets/images/drinks/beer.png'
import cocacolaImg from '/src/assets/images/drinks/cocacola.png'
import fantaImg from '/src/assets/images/drinks/fanta.png'
import spriteImg from '/src/assets/images/drinks/sprite.png'

const drinks = [
    {
        name: 'Water',
        imgSrc: waterImg,
        price: 1.50
    },
    {
        name: 'Beer',
        imgSrc: beerImg,
        price: 4.00
    },
    {
        name: 'CocaCola',
        imgSrc: cocacolaImg,
        price: 2.50
    },
    {
        name: 'Fanta',
        imgSrc: fantaImg,
        price: 2.50
    },
    {
        name: 'Sprite',
        imgSrc: spriteImg,
        price: 2.50
    }
]

const handleCart = () => {
    alert('Added to cart')
}
</script>

<style scoped>

</style>