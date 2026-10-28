<script>
import image1 from '../assets/popularMeal.png'
import image2 from '../assets/popularMeals.png'
import image3 from '../assets/popularDesserts.png'
import image4 from '../assets/popularSnack.png'
import image5 from '../assets/popularSnacks.png'

export default {
    props: ['forFoods'],
    emits: ['gotoMeal', 'gotoSnack', 'gotoDrink', 'gotoDessert'],
    data() {
        return {
            populars: [
                {
                    id: 1,
                    name: 'SALMON',
                    image: image1,
                },
                {
                    id: 2,
                    name: 'BEEF STEAK',
                    image: image2,
                },
                {
                    id: 3,
                    name: 'BELGIAN WAFFLE',
                    image: image3,
                },
                {
                    id: 4,
                    name: 'GOURMET FRIES',
                    image: image4,
                },
                {
                    id: 5,
                    name: 'BEEF NACHOS',
                    image: image5,
                },
            ]
        }
    },
    methods: {
        clickMeal() {
            this.$emit('gotoMeal');
        },
        clickSnack() {
            this.$emit('gotoSnack');
        },
        clickDrink() {
            this.$emit('gotoDrink');
        },
        clickDessert() {
            this.$emit('gotoDessert');
        }
    }
}
</script>

<template>
    <div class="bg-black/90 w-full min-h-screen flex flex-col gap-10 items-center pt-15 pb-20 px-10">

        <div class="">
            <h1 class="text-white text-4xl font-bold text-start w-full max-w-6xl">
                Welcome to
                <span class="font-serif italic"> <br>
                    Silingan
                </span>
            </h1>
        </div>

        <!-- Categories Section -->
        <div class="w-full max-w-6xl flex flex-wrap justify-center gap-8 z-10">

            <div @click="clickMeal"
                class="w-40 h-40 border px-5 py-2 border-yellow-400 rounded-lg items-center flex flex-col justify-between cursor-pointer hover:bg-yellow-500 duration-300">
                <img src="../assets/meals.png" alt="Meals" class="w-20 h-20 object-contain">
                <p class="text-white text-center font-semibold">Meals</p>
            </div>

            <div @click="clickSnack"
                class="w-40 h-40 border px-5 py-2 border-yellow-400 rounded-lg items-center flex flex-col justify-between cursor-pointer hover:bg-yellow-500 duration-300">
                <img src="../assets/snacks.png" alt="Snacks" class="w-20 h-20 object-contain">
                <p class="text-white text-center font-semibold">Snacks</p>
            </div>

            <div @click="clickDrink"
                class="w-40 h-40 border px-5 py-2 border-yellow-400 rounded-lg items-center flex flex-col justify-between cursor-pointer hover:bg-yellow-500 duration-300">
                <img src="../assets/drinks.png" alt="Drinks" class="w-16 h-20 object-contain">
                <p class="text-white text-center font-semibold">Drinks</p>
            </div>

            <div @click="clickDessert"
                class="w-40 h-40 border px-6 py-2 border-yellow-400 rounded-lg items-center flex flex-col justify-between cursor-pointer hover:bg-yellow-500 duration-300">
                <img src="../assets/desserts.png" alt="Dessert" class="w-20 h-20 object-contain">
                <p class="text-white text-center font-semibold">Dessert</p>
            </div>

        </div>

        <h1 class="text-white text-2xl font-semibold text-start w-full max-w-6xl pl-35">
            Popular Dish
        </h1>

        <!-- Popular Dishes Section -->
        <div class="">

            <div
                class="flex justify-center gap-5 relative w-full grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-5">
                <div v-for="popular in populars" :key="popular.id" class="flex relative z-99">
                    <div class="relative">
                        <img :src="popular.image" alt="" class="w-25 h-25 absolute top-0 left-8">

                        <div
                            class=" mt-13 border w-43 h-35 border-orange-600 rounded-lg flex flex-col items-center gap-5 px-5  pt-17 cursor-pointer hover:bg-orange-700">

                            <div>
                                <hr class="  border-white w-full">
                                <p class="text-white text-center">{{ popular.name }}</p>
                                <hr class="  border-white w-full">
                            </div>


                        </div>
                    </div>

                </div>
            </div>
        </div>
    </div>
</template>