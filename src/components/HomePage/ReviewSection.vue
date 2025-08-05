<template>
    <div class="h-fit">
        <h1 class="text-center text-2xl sm:text-3xl lg:text-4xl xl:text-5xl 2xl:text-6xl font-bold my-5">What are people saying?</h1>

        <button class="block xl:text-xl my-8 mx-auto w-fit font-bold bg-amber-500 p-4 text-darkgray"><i class="fa-solid fa-comment-dots"></i> Leave your review <i class="fa-solid fa-comment-dots"></i></button>

        <div class="scroll flex flex-row overflow-x-auto snap-x">
            <ReviewItem class="w-fit h-fit p-12 sm:size-140 lg:size-160 xl:size-180 2xl:size-230 shrink-0 snap-center" v-for="review in reviews" :imgSrc="review.imgSrc" :reviewHeading="review.reviewHeading" :review="review.review" :name="review.name"/>
        </div>
    </div>
</template>

<script setup lang="ts">
import ReviewItem from './ReviewSection/ReviewItem.vue';

import SarahReviewImg from '/src/assets/images/reviewImages/image1.webp'
import MikeReviewImg from '/src/assets/images/reviewImages/image2.webp'
import JesscaReviewImg from '/src/assets/images/reviewImages/image3.webp'
import RobertReviewImg from '/src/assets/images/reviewImages/image4.webp'
import AmandaReviewImg from '/src/assets/images/reviewImages/image5.webp'
import DavidReviewImg from '/src/assets/images/reviewImages/image6.webp'

const reviews = [
    {
        imgSrc: SarahReviewImg,
        reviewHeading: '"Best pizza in town, hands down!"',
        review: 'Been coming here for two years and the quality never disappoints. Perfect crust - crispy outside, chewy inside. The margherita is amazing and staff is always friendly. Our Friday night tradition!',
        name: 'Sarah M.'
    },
    {
        imgSrc: MikeReviewImg,
        reviewHeading: '"Great atmosphere for families"',
        review: 'Brought my kids for my son\'s birthday and they loved it! Staff was super patient with our group. Kids devoured the pepperoni pizza, and the prosciutto and arugula was excellent. Great portions and prices too.',
        name: 'Mike R.'
    },
    {
        imgSrc: JesscaReviewImg,
        reviewHeading: '"Amazing variety and dietary options"',
        review: 'Finally found a pizza place with great gluten-free options! The crust actually tastes good, not like cardboard. Mediterranean pizza with feta and sun-dried tomatoes was delicious. Great vegan cheese too!',
        name: 'Jessica L.'
    },
    {
        imgSrc: RobertReviewImg,
        reviewHeading: '"Outstanding service and quality ingredients"',
        review: 'You can taste the difference with quality ingredients here. Fresh homemade sauce, perfect cheese, and that Italian sausage is clearly made in-house. Professional service and worth every penny!',
        name: 'Robert K.'
    },
    {
        imgSrc: AmandaReviewImg,
        reviewHeading: '"Perfect for date night"',
        review: 'Come here monthly for date. Cozy lighting, nice wine selection, and the quattro stagioni pizza is our favorite. Service is excellent and they never rush you. Perfect romantic atmosphere!',
        name: 'Amanda T.'
    },
    {
        imgSrc: DavidReviewImg,
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