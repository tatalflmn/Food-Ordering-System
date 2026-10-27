<script>

export default {
    props: ['forFoods'],
    data() {
        return {

        }
    }, methods: {

    }
}

</script>


<template>

    <!-- FOODS -->
    <div class="px-10 py-5 bg-black ">

        <form class="mt-10 mx-auto max-w-xl py-2 px-6 rounded-full bg-gray-50 border flex focus-within:border-gray-300">
            <input type="text" placeholder="Search here"
                class="bg-transparent w-full focus:outline-none pr-4 font-semibold border-0 focus:ring-0 px-0 py-0"
                name="topic"><button
                class="flex flex-row items-center justify-center min-w-[130px] px-4 rounded-full font-medium tracking-wide border cursor-pointer disabled:opacity-50 transition ease-in-out duration-150 text-base bg-black text-white font-medium tracking-wide border-transparent py-1.5 h-[38px] -mr-3">
                Search
            </button>
        </form>

        <div class="flex justify-between items-center px-48">
            <h1 class="text-3xl font-bold italic text-center text-white m-10">Food Menu :</h1>
            <p class="text-2xl text-white cursor-pointer hover:scale-105 duration-500">X</p>
        </div>
        <section class="grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-4 px-45">

            <div v-for="food in forFoods" :key="food.id"
                class="food-card relative rounded-[28px] border border-stone-100 bg-white p-5 shadow-lg" :class="index === 1
                    ? 'bg-amber-400'
                    : ''">

                <!-- Food Image -->
                <div class="relative mb-5 flex justify-center pt-2">

                    <span
                        class="absolute left-0 top-0 z-10 rounded-full bg-rose-500 px-3 py-1 text-xs font-bold text-white shadow">
                        Popular
                    </span>

                    <img :src="food.image" :alt="food.name"
                        class="food-image h-40 w-40 rounded-full object-cover shadow-xl ring-4" :class="index === 1
                            ? 'ring-white/50'
                            : 'ring-stone-100'">

                </div>

                <!-- Food Name -->
                <h3 class="min-h-13 text-center text-xl font-extrabold" :class="index === 1
                    ? 'text-white'
                    : 'text-stone-900'">
                    {{ food.name }}
                </h3>

                <p>{{ food.description }}</p>


                <!-- Price and Add Button -->
                <div class="mt-5 flex items-center justify-between">

                    <div>
                        <p class="text-2xl font-extrabold" :class="index === 1
                            ? 'text-white'
                            : 'text-stone-900'">
                            ₱{{ food.price }}
                        </p>

                        <p class="mt-1 text-xs" :class="index === 1
                            ? 'text-white/80'
                            : 'text-stone-400'">
                            Per serving
                        </p>
                    </div>

                    <button
                        class="add-button flex h-11 w-11 items-center justify-center rounded-full bg-amber-400 text-3xl font-light text-white shadow-md hover:bg-amber-500 hover:scale-105 duration-300 cursor-pointer">
                        +
                    </button>

                </div>

            </div>

        </section>
    </div>


</template>