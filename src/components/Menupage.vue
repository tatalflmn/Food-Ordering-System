<script>
import image1 from '../assets/popularMeal.png'
import image2 from '../assets/popularMeals.png'
import image3 from '../assets/popularDessert.png'
import image4 from '../assets/popularSnacks2.png'

export default {
    data() {
        return {
            populars: [
                {
                    id: 1,
                    name: 'Salmon with Caviar',
                    image: image1,
                    price: 200
                },
                {
                    id: 1,
                    name: 'Pork Stew Kare-Kare',
                    image: image2,
                    price: 200
                },
                {
                    id: 1,
                    name: 'Cookie Ice Cream Choco Drizzled',
                    image: image3,
                    price: 200
                },
                {
                    id: 1,
                    name: 'Salmon with Caviar',
                    image: image4,
                    price: 200
                },
              

            ]
        }
    }, methods: {

    }
}
</script>

<template>

    <div class="bg-black w-full h-screen flex flex-col gap-10 items-center pt-5 pl-40">

        <h1 class="text-white text-4xl font-bold text-start w-full pl-25">Welcome to
            <span class="font-serif italic"> <br>
                Silingan
            </span>
        </h1>

        <div class="w-290 flex gap-15">

            <div
                class="w-fit h-40 border px-5 py-1  border-orange-800 rounded-lg items-center flex flex-col justify-between cursor-pointer hover:bg-orange-700">
                <img src="../assets/meals.png" alt="" class="w-25 h-25">
                <p class="text-white text-center ">Meals</p>
            </div>

            <div
                class="w-fit h-40 border px-5 py-1  border-orange-800 rounded-lg items-center flex flex-col justify-between cursor-pointer hover:bg-orange-700">
                <img src="../assets/snacks.png" alt="" class="w-25 h-25">
                <p class="text-white text-center ">Snack</p>
            </div>


            <div
                class="w-fit h-40 border px-5 py-1  border-orange-800 rounded-lg items-center flex flex-col justify-between cursor-pointer hover:bg-orange-700">
                <img src="../assets/desserts.png" alt="" class="w-25 h-25">
                <p class="text-white text-center ">Dessert</p>
            </div>

            <div
                class="w-36 h-40 border px-6 py-1  border-orange-800 rounded-lg items-center flex flex-col justify-between cursor-pointer hover:bg-orange-700">
                <img src="../assets/drinks.png" alt="" class="w-19 h-25">
                <p class="text-white text-center ">Drinks</p>
            </div>

        </div>


        <h1 class="text-white text-2xl font-semibold text-start w-full pl-25">
            Popular Dish
        </h1>

        <div class="flex gap-5 w-290 relative z-99">
            <div v-for="popular in populars" :key="popular.id" class="flex relative z-99">
                <div class="relative">
                    <img :src="popular.image" alt="" class="w-25 h-25 absolute top-0 left-8">
    
                    <div
                        class=" mt-13 border w-43 h-45 border-orange-800 rounded-lg flex flex-col items-center gap-5 px-5  pt-17 cursor-pointer hover:bg-orange-700">
    
                        <div>
                            <hr class="  border-white w-full">
                            <p class="text-white text-center">{{ popular.name }}</p>
                            <hr class="  border-white w-full">
                        </div>
    
                        <div class="flex justify-between items-center w-full">
                            <p class="text-white text-xl">₱ {{popular.price }}</p>
    
                            <div
                                class=" bg-white rounded-xl px-2  flex items-center  cursor-pointer hover:bg-black hover:text-white">
                                <p class=" text-2xl">+</p>
                            </div>
    
                        </div>
                    </div>
                </div>
    
            </div>
        </div>
    </div>
</template>