<script setup>
import { ref, reactive } from 'vue';

const photoLightOn = ref("//img.icons8.com/?size=512&id=12244&format=png")
const photoLightOff = ref("//img.icons8.com/?size=512&id=75&format=png")
const colorLightOn = ref("bg-blue-500 hover:bg-blue-700")
const colorLightOff = ref("bg-gray-500 hover:bg-gray-700")

const lights = reactive([
    { name: "Light 1", status: true, val: "On" },
    { name: "Light 2", status: false, val: "Off" },
    { name: "Light 3", status: false, val: "Off" }
])
</script>

<template>
    <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Assignment</h1>
        <p class="p-5">Make These Buttons Work</p>
        <div class="flex justify-between space-x-6">
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <button v-for="(light,index) in lights" @click="lights[index].status = !lights[index].status" :class="lights[index].status==true?colorLightOn:colorLightOff" class="text-white font-bold py-2 px-4 rounded" :hover="index">
                    {{ lights[index].name }} {{ lights[index].status == true?'On':'Off' }}
                </button>
            </div>
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <img v-for="i in lights.length" class="w-20" :src="lights[i-1].status==true?photoLightOn:photoLightOff" alt="">
            </div>
        </div>
    </section>
</template>

<style scoped>
    
</style>