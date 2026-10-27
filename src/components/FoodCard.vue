<script>
export default {
    name: 'FoodCard',
    props: ['forFoods'],
    data() {
        return {
            searchQuery: ''
        }
    },
    computed: {
        displayedFoods() {
            if (!this.searchQuery) return this.forFoods;
            return this.forFoods.filter(food => 
                (food.name || '').toLowerCase().includes(this.searchQuery.toLowerCase()) ||
                (food.description || '').toLowerCase().includes(this.searchQuery.toLowerCase())
            );
        }
    },
    methods: {
        closeCard() {
            this.$emit('close');
        },
        addToCart(food) {
            this.$emit('add-to-cart', food);
        }
    }
}
</script>

<template>
    <div class="px-6 py-5 bg-black min-h-screen pl-44">
        <!-- Search Form -->
        <form @submit.prevent class="mt-10 mx-auto max-w-xl py-2 px-6 rounded-full bg-gray-50 border flex focus-within:border-gray-300">
            <input 
                type="text" 
                v-model="searchQuery" 
                placeholder="Search here..."
                class="bg-transparent w-full focus:outline-none pr-4 font-semibold border-0 focus:ring-0 px-0 py-0"
                name="topic"
            >
            <button class="flex flex-row items-center justify-center min-w-[130px] px-4 rounded-full font-medium tracking-wide border cursor-pointer transition ease-in-out duration-150 text-base bg-black text-white border-transparent py-1.5 h-[38px] -mr-3">
                Search
            </button>
        </form>

        <div class="flex justify-between items-center max-w-7xl mx-auto px-4 md:px-12">
            <h1 class="text-3xl font-bold italic text-center text-white m-10">Food Menu :</h1>
            <p @click="closeCard" class="text-2xl text-white cursor-pointer hover:scale-105 duration-500">X</p>
        </div>

        <section class="grid grid-cols-1 gap-5 sm:grid-cols-2 lg:grid-cols-4 max-w-7xl mx-auto px-4 md:px-12 pb-10">
            <div v-for="(food, index) in displayedFoods" :key="food.id"
                class="food-card relative rounded-[28px] border border-stone-100 bg-white p-5 shadow-lg flex flex-col justify-between" 
                >
                <div>
                    <!-- Food Image -->
                    <div class="relative mb-5 flex justify-center pt-2">
                        <span class="absolute left-0 top-0 z-10 rounded-full bg-rose-500 px-3 py-1 text-xs font-bold text-white shadow">
                            Popular
                        </span>
                        <img :src="food.image" :alt="food.name"
                            class="food-image h-40 w-40 rounded-full object-cover shadow-xl ring-4" 
                        >
                    </div>

                    <!-- Food Name -->
                    <h3 class="min-h-13 text-center text-xl font-extrabold">
                        {{ food.name }}
                    </h3>

                    <p class="text-stone-600 text-center text-sm mt-2">
                        {{ food.description }}
                    </p>
                </div>

                <!-- Price and Add Button -->
                <div class="mt-5 flex items-center justify-between">
                    <div>
                        <p class="text-2xl font-extrabold">
                            ₱{{ food.price }}
                        </p>
                        <p class="mt-1 text-xs text-gray-500">
                            Per serving
                        </p>
                    </div>

                    <!-- CONNECTED: Emits add-to-cart on click -->
                    <button 
                        @click="addToCart(food)"
                        class="add-button flex h-11 w-11 items-center justify-center rounded-full bg-amber-400 text-3xl font-light text-white shadow-md hover:bg-amber-500 hover:scale-105 duration-300 cursor-pointer"
                    >
                        +
                    </button>
                </div>
            </div>
        </section>
    </div>
</template>