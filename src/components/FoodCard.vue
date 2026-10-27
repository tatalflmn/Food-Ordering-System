<script>
export default {
    name: 'FoodCard',
    props: ['forFoods'],
    data() {
        return {
            searchQuery: '',
            isModalOpen: false,
            selectedFood: null
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
        },
        openDetails(food) {
            this.selectedFood = food;
            this.isModalOpen = true;
        },
        closeDetails() {
            this.isModalOpen = false;
            this.selectedFood = null;
        }
    }
}
</script>

<template>
    <div class="px-6 py-5 bg-black min-h-screen pl-44 relative">
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
            <div v-for="food in displayedFoods" :key="food.id"
                class="food-card relative rounded-[28px] border border-stone-100 bg-white p-5 shadow-lg flex flex-col justify-between" 
                >
                <div>
                    <!-- Food Image (Clickable to open modal) -->
                    <div class="relative mb-5 flex justify-center pt-2">
                        <span class="absolute left-0 top-0 z-10 rounded-full bg-rose-500 px-3 py-1 text-xs font-bold text-white shadow">
                            Popular
                        </span>
                        <img :src="food.image" :alt="food.name"
                            @click="openDetails(food)"
                            class="food-image h-40 w-40 rounded-full object-cover shadow-xl ring-4 cursor-pointer hover:scale-105 transition-transform duration-300" 
                        >
                    </div>

                    <!-- Food Name -->
                    <h3 class="min-h-13 text-center text-xl font-extrabold">
                        {{ food.name }}
                    </h3>
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

                    <button 
                        @click="addToCart(food)"
                        class="add-button flex h-11 w-11 items-center justify-center rounded-full bg-amber-400 text-3xl font-light text-white shadow-md hover:bg-amber-500 hover:scale-105 duration-300 cursor-pointer"
                    >
                        +
                    </button>
                </div>
            </div>
        </section>

        <!-- DETAILS MODAL -->
        <div v-if="isModalOpen" class="fixed inset-0 z-50 flex justify-center items-center bg-black/70 backdrop-blur-sm">
            <div class="w-full max-w-md pb-5 bg-black rounded-2xl shadow-[0_0_40px_white]  border border-gray-800">
                <!-- Header -->
                <div class="bg-gray-800 w-full px-6 py-4 flex items-center justify-between rounded-t-2xl">
                    <div class="w-6"></div>
                    <h1 class="text-2xl font-extrabold text-white text-center">
                        Details
                    </h1>
                    <button 
                        @click="closeDetails" 
                        class="text-2xl cursor-pointer text-gray-400 hover:text-white font-bold leading-none"
                    >
                        ✕
                    </button>
                </div>

                <!-- Dynamic Food Image -->
                <div class="flex justify-center">
                    <img 
                        class="w-40 h-40 mt-5 rounded-full object-cover shadow-[0_0_40px_white]"
                        :src="selectedFood.image" 
                        :alt="selectedFood.name"
                    >
                </div>

                <!-- Dynamic Title -->
                <div class="flex justify-center">
                    <h2 class="text-white font-bold text-3xl pt-4 text-center px-4">
                        {{ selectedFood.name }}
                    </h2>
                </div>

                <!-- Rating Section (Static/Default 3.7) -->
                <div class="flex justify-center gap-1 pt-2">
                    <svg v-for="i in 5" :key="i" xmlns="http://www.w3.org/2000/svg" class="text-yellow-500 w-6 h-6 fill-current" viewBox="0 0 16 16">
                        <path d="M3.612 15.443c-.386.198-.824-.149-.746-.592l.83-4.73L.173 6.765c-.329-.314-.158-.888.283-.95l4.898-.696L7.538.792c.197-.39.73-.39.927 0l2.184 4.327 4.898.696c.441.062.612.636.282.95l-3.522 3.356.83 4.73c.078.443-.36.79-.746.592L8 13.187l-4.389 2.256z" />
                    </svg>
                </div>

                <div class="flex justify-center pt-1">
                    <span class="text-slate-400 font-medium text-sm">3.7 out of 5 stars • ₱{{ selectedFood.price }}</span>
                </div>

                <!-- Dynamic Description -->
                <div class="px-6 pt-4">
                    <p class="text-gray-300 text-base text-center leading-relaxed">
                        {{ selectedFood.description }}
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>