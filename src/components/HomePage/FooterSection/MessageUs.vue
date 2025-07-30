<template>
    <div id="contacts"  class="h-fit py-10 flex flex-col bg-black text-white gap-5">
        <h1 class="text-center text-2xl font-bold">Message us</h1>

        <div class="flex flex-col gap-8 mx-auto">
            <input class="border-b-2 text-sm py-2 focus:outline-0" placeholder="First Name" id="firstName" name="firstName" type="text" required v-model="firstName">
            <input class="border-b-2 text-sm py-2 focus:outline-0" placeholder="Last Name" id="lastName" name="lastName" type="text" required v-model="lastName">       
            <input class="border-b-2 text-sm py-2 focus:outline-0" placeholder="Message" id="message" name="message" type="text" required v-model="message">
        </div>

        <button @click="sendMessage"  class="block my-5 mx-auto w-[35vh] font-bold bg-amber-500 p-3 text-black transition active:scale-120 active:-translate-y-4">Send</button>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const firstName = ref<string>('')
const lastName = ref<string>('')
const message = ref<string>('')

const sendMessage = () => {
    firstName.value = ''
    lastName.value = ''
    message.value = ''
}


</script>

<style scoped>

</style>