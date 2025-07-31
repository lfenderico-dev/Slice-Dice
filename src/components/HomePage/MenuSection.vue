<template>
    <div id="menu"  class="h-fit bg-darkgray pb-15">
        <h1 class="text-white text-2xl sm:text-3xl font-bold text-center pt-8">Menu</h1>
        <hr class="mx-auto w-10 h-2 bg-amber-500 border-0 rounded-sm">

        <div class="flex flex-col py-10 text-white text-lg sm:text-xl gap-5">
            <button @click="category = 'pizza'"  class="font-bold mx-auto w-fit shadow-black shadow-2xl px-25 py-3 transition active:scale-120 active:-translate-y-4">Pizza</button>
            <button @click="category = 'appetizers'"  class="font-bold mx-auto w-fit shadow-black shadow-2xl px-25 py-3 transition active:scale-120 active:-translate-y-4">Appetizer</button>
            <button @click="category = 'drinks'"  class="font-bold mx-auto w-fit shadow-black shadow-2xl px-25 py-3 transition active:scale-120 active:-translate-y-4">Drinks</button>
        </div>

        <!-- Pizzas div -->
        <div v-if="category == 'pizza' || category == null"   class="flex flex-col gap-10">
            <MenuItem v-for="pizza in pizzas" :name="pizza.name" :description="pizza.description" :img-src="pizza.imgSrc" :price="pizza.price" @addToCart="handleCart"/>
        </div>

        <!-- Appetizers div -->
        <div v-if="category == 'appetizers'" class="flex flex-col gap-10">
            <MenuItem v-for="appetizer in appetizers" :name="appetizer.name" :description="appetizer.description" :img-src="appetizer.imgSrc" :price="appetizer.price" @addToCart="handleCart"/>
        </div>

        <!-- Drinks div -->
        <div v-if="category == 'drinks'" class="flex flex-col gap-10">
            <MenuItem v-for="drink in drinks" :name="drink.name" :img-src="drink.imgSrc" :price="drink.price" @addToCart="handleCart"/>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const category = ref<string | null>(null)


import MenuItem from './MenuSection/MenuItem.vue';

const pizzas = [
    {
        name: 'Margherita',
        imgSrc: '/src/assets/images/pizzas/margherita.jpg',
        description: 'San Marzano tomato base, fresh mozzarella fior di latte, fresh basil leaves and a drizzle of extra virgin olive oil',
        price: 6.50
    },
    {
        name: 'Marinara',
        imgSrc: '/src/assets/images/pizzas/marinara.png',
        description: 'Tomato sauce flavored with fresh garlic, Sicilian oregano and generous seasoning of extra virgin olive oil',
        price: 5.00
    },
    {
        name: 'Quattro Stagioni',
        imgSrc: '/src/assets/images/pizzas/4stagioni.png',
        description: 'Tomato, mozzarella fior di latte, sweet cooked ham, fresh champignon mushrooms, artichokes in oil and Taggiasca black olives',
        price: 8.50
    },
    {
        name: 'Bufalina',
        imgSrc: '/src/assets/images/pizzas/bufalina.jpg',
        description: 'San Marzano DOP tomato, premium Campanian buffalo mozzarella, fresh basil and Apulian extra virgin olive oil',
        price: 9.00
    },
    {
        name: 'Diavola',
        imgSrc: '/src/assets/images/pizzas/diavola.jpg',
        description: 'Spicy tomato base, stringy mozzarella and abundant thinly sliced Calabrian spicy salami',
        price: 7.50
    },
    {
        name: 'Ortolana',
        imgSrc: '/src/assets/images/pizzas/ortolana.jpg',
        description: 'Light tomato, mozzarella, grilled zucchini, diced eggplant, colorful bell peppers and cherry tomatoes',
        price: 8.00
    },
    {
        name: 'Montanara',
        imgSrc: '/src/assets/images/pizzas/montanara.jpg',
        description: 'Rustic tomato, mozzarella, sautéed porcini mushrooms, crumbled mountain sausage and fresh rosemary sprigs',
        price: 9.50
    }
]

const appetizers = [
    {
        name: 'Bruschetta',
        imgSrc: '/src/assets/images/appetizers/bruschette.jpg',
        description: 'Toasted Apulian bread rubbed with fresh garlic, diced ripe tomatoes, fragrant basil and extra virgin olive oil',
        price: 4.50
    },
    {
        name: 'Salumi',
        imgSrc: '/src/assets/images/appetizers/salumi.jpg',
        description: 'Selection of artisanal cured meats: Parma prosciutto, spicy salami, aged coppa, served with warm focaccia and pickled vegetables',
        price: 10.00
    },
    {
        name: 'Caprese',
        imgSrc: '/src/assets/images/appetizers/caprese.jpg',
        description: 'Campanian buffalo mozzarella DOP, ripe San Marzano tomatoes, fresh basil and a drizzle of Apulian extra virgin olive oil',
        price: 8.50
    },
    {
        name: 'Antipasto di mare',
        imgSrc: '/src/assets/images/appetizers/antipastoDiMare.png',
        description: 'Marinated octopus with celery and olives, pink shrimp, gratinated mussels, lemon-marinated anchovies and creamy baccalà',
        price: 14.00
    },
    {
        name: 'Suppli',
        imgSrc: '/src/assets/images/appetizers/suppli.png',
        description: 'Roman rice croquettes with tomato stuffed with stringy mozzarella, breaded and fried to golden perfection',
        price: 5.00
    },
    {
        name: 'Frittatina',
        imgSrc: '/src/assets/images/appetizers/frittatina.png',
        description: 'Traditional Neapolitan fried pasta omelet with spaghetti, eggs, pecorino cheese, black pepper and fresh herbs',
        price: 4.50
    }
]

const drinks = [
    {
        name: 'Water',
        imgSrc: '/src/assets/images/drinks/water.png',
        price: 1.50
    },
    {
        name: 'Beer',
        imgSrc: '/src/assets/images/drinks/beer.png',
        price: 4.00
    },
    {
        name: 'CocaCola',
        imgSrc: '/src/assets/images/drinks/cocacola.png',
        price: 2.50
    },
    {
        name: 'Fanta',
        imgSrc: '/src/assets/images/drinks/fanta.png',
        price: 2.50
    },
    {
        name: 'Sprite',
        imgSrc: '/src/assets/images/drinks/sprite.png',
        price: 2.50
    }
]

const handleCart = () => {
    alert('Added to cart')
}
</script>

<style scoped>

</style>