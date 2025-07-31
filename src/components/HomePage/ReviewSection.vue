<template>
    <div class="h-fit">
        <h1 class="text-center text-2xl sm:text-3xl font-bold my-5">What are people saying?</h1>

        <button class="block my-8 mx-auto w-fit font-bold bg-amber-500 p-4 text-darkgray"><i class="fa-solid fa-comment-dots"></i> Leave your review <i class="fa-solid fa-comment-dots"></i></button>

        <div class="scroll flex flex-row overflow-x-auto snap-x">
            <ReviewItem class="w-fit h-fit sm:size-120 shrink-0 snap-center" v-for="review in reviews" :imgSrc="review.imgSrc" :reviewHeading="review.reviewHeading" :review="review.review" :name="review.name"/>
        </div>
    </div>
</template>

<script setup lang="ts">
import ReviewItem from './ReviewSection/ReviewItem.vue';

const reviews = [
    {
        imgSrc: '/src/assets/images/reviewImages/image1.png',
        reviewHeading: '"Best pizza in town, hands down!"',
        review: 'Been coming here for two years and the quality never disappoints. Perfect crust - crispy outside, chewy inside. The margherita is amazing and staff is always friendly. Our Friday night tradition!',
        name: 'Sarah M.'
    },
    {
        imgSrc: '/src/assets/images/reviewImages/image2.png',
        reviewHeading: '"Great atmosphere for families"',
        review: 'Brought my kids for my son\'s birthday and they loved it! Staff was super patient with our group. Kids devoured the pepperoni pizza, and the prosciutto and arugula was excellent. Great portions and prices too.',
        name: 'Mike R.'
    },
    {
        imgSrc: '/src/assets/images/reviewImages/image3.png',
        reviewHeading: '"Amazing variety and dietary options"',
        review: 'Finally found a pizza place with great gluten-free options! The crust actually tastes good, not like cardboard. Mediterranean pizza with feta and sun-dried tomatoes was delicious. Great vegan cheese too!',
        name: 'Jessica L.'
    },
    {
        imgSrc: '/src/assets/images/reviewImages/image4.png',
        reviewHeading: '"Outstanding service and quality ingredients"',
        review: 'You can taste the difference with quality ingredients here. Fresh homemade sauce, perfect cheese, and that Italian sausage is clearly made in-house. Professional service and worth every penny!',
        name: 'Robert K.'
    },
    {
        imgSrc: '/src/assets/images/reviewImages/image5.png',
        reviewHeading: '"Perfect for date night"',
        review: 'Come here monthly for date. Cozy lighting, nice wine selection, and the quattro stagioni pizza is our favorite. Service is excellent and they never rush you. Perfect romantic atmosphere!',
        name: 'Amanda T.'
    },
    {
        imgSrc: '/src/assets/images/reviewImages/image6.png',
        reviewHeading: '"Exceeded expectations for delivery"',
        review: 'Didn\'t expect much from delivery but was pleasantly surprised! Pizza arrived hot and fresh with great texture. Meat lovers was loaded with toppings and full of flavor. Now our go-to for busy weeknights!',
        name: 'David H.'
    }
]

</script>

<style scoped>
.scroll::-webkit-scrollbar {
  display: none;
}
.scroll {
  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;     /* Firefox */
}
</style>