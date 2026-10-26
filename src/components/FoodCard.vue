<script>

export default {
    data() {
        return {

            meals: [
                {
                    id: 1,
                    name: 'CHICKEN POTATO',
                    price: 220,
                    image: 'https://i.pinimg.com/736x/04/39/47/04394754d461573412134b960a6130fe.jpg',
                    description: 'chicken potato a hearty, satisfying, and deeply savory profile.'

                },
                {
                    id: 2,
                    name: 'SALMON',
                    price: 300,
                    image: 'https://i.pinimg.com/736x/02/20/81/022081ead8a4632c56a3e2c04d942d64.jpg',
                    description: 'flaky pink fish with a rich, buttery flavor and crisp skin'

                },
                {
                    id: 3,
                    name: 'SHRIMP',
                    price: 210,
                    image: 'https://i.pinimg.com/1200x/65/de/59/65de59148c35150f2c64da8f36dbc5cd.jpg',
                    description: 'a culinary seafood dish made with fresh or frozen shrimp.'

                },
                {
                    id: 4,
                    name: 'BEEF STICK',
                    price: 200,
                    image: 'https://i.pinimg.com/1200x/b4/b5/96/b4b5961674d0103249a7ad249972c66c.jpg',
                    description: 'featuring thinly sliced beef braised in soy sauce and citrus.'

                },
                {
                    id: 5,
                    name: 'LETCHON BELLY',
                    price: 250,
                    image: 'https://i.pinimg.com/1200x/b3/30/5b/b3305b49db5af4ba7934c453b18afed0.jpg',
                    description: 'classic flavors of whole-pig lechon on a smaller, convenient scale.'

                },
                {
                    id: 6,
                    name: 'CHICKEN BUFFALO',
                    price: 200,
                    image: 'https://i.pinimg.com/1200x/33/f8/f9/33f8f955b818f768e7a463f53a1cbea6.jpg',
                    description: 'traditionally fried wings or baked/grilled chicken breasts.'

                },
                {
                    id: 7,
                    name: 'CHICKEN SKEWERS',
                    price: 280,
                    image: 'https://i.pinimg.com/736x/f8/90/5f/f8905fb9a92dcce4cad6a1de300c782f.jpg',
                    description: 'marinated chicken breast or thigh threaded onto wooden or metal sticks.'

                },
                {
                    id: 8,
                    name: 'CARBONARA',
                    price: 250,
                    image: 'https://i.pinimg.com/736x/d5/13/84/d513842a5df920975b0354d8d2df06ea.jpg',
                    description: 'glossy sauce of eggs, hard cheese, cured pork, and black pepper.'

                },

            ],

            snacks: [
                {
                    id: 1,
                    name: 'CHURROS',
                    price: 220,
                    image: 'https://i.pinimg.com/1200x/23/cc/17/23cc176e7e967058152d2dcb51a5f7fc.jpg',
                    description: 'ridged, deep-fried choux pastry sticks coated in cinnamon sugar.'

                },
                {
                    id: 2,
                    name: 'MOZZARELLA STICKS',
                    price: 300,
                    image: 'https://i.pinimg.com/1200x/b7/96/d6/b796d636c0055dda3875ff0ba1bd2cef.jpg',
                    description: 'deep-fried made from elongated pieces of mozzarella cheese.'

                },
                {
                    id: 3,
                    name: 'BANANA SPLIT',
                    price: 210,
                    image: 'https://i.pinimg.com/236x/b1/5f/77/b15f77c5fb89bfc42f1c86c20466f605.jpg',
                    description: 'a peeled banana in half lengthwise and placing it in a long dish.'

                },
                {
                    id: 4,
                    name: 'FRIES GOURMENT',
                    price: 200,
                    image: 'https://i.pinimg.com/736x/56/85/94/568594ff03c43418b3a3b913553e01d3.jpg',
                    description: 'deep-fried strips of potato featuring a crispy exterior and a soft, fluffy interior.'

                },
                {
                    id: 5,
                    name: 'MEAT BALLS',
                    price: 250,
                    image: 'https://i.pinimg.com/736x/6a/7d/cd/6a7dcd1a64bf68b6b0ef12c552949978.jpg',
                    description: 'a small, round sphere made from chopped or ground meat'

                },
                {
                    id: 6,
                    name: 'BURGER WITH FRIES',
                    price: 200,
                    image: 'https://i.pinimg.com/1200x/58/5a/71/585a71fd86e109b465027a49c1cd84bd.jpg',
                    description: 'a hearty, savory comfort meal pairing a warm, meat-filled sandwich.'

                },
                {
                    id: 7,
                    name: 'BEEF NACHOS',
                    price: 280,
                    image: 'https://i.pinimg.com/1200x/0d/85/09/0d85096318a1fe35edf41121a775c503.jpg',
                    description: 'crisp corn tortilla chips, layered or topped with savory beef and cheese.'

                },
                {
                    id: 8,
                    name: 'CRUNCHY COOKIES',
                    price: 250,
                    image: 'https://i.pinimg.com/736x/8e/9d/b6/8e9db66afe221bf69e2dce0bb91aa15f.jpg',
                    description: 'driven by a lower moisture content and specific ingredient ratios.'

                },

            ],


            drinks: [
                {
                    id: 1,
                    name: 'COCKTAILS',
                    price: 220,
                    image: 'https://i.pinimg.com/736x/bb/d2/ea/bbd2ea0272a9f108ada78b7b03f9257a.jpg',
                    description: 'Smade by combining a distilled spirit with other ingredients.'

                },
                {
                    id: 2,
                    name: 'FRUITY DRINKS',
                    price: 300,
                    image: 'https://i.pinimg.com/736x/68/59/e9/6859e9081fa489b6c312d82fe1a4588c.jpg',
                    description: 'cooked fruit flavor profile rather than a single narrow spice.'

                },
                {
                    id: 3,
                    name: 'ICE TEA LEMON',
                    price: 210,
                    image: 'https://i.pinimg.com/1200x/80/15/4c/80154c2c9b7008f13e1e821ccd680cb3.jpg',
                    description: 'a cold, refreshing beverage made by combining chilled brewed tea'

                },
                {
                    id: 4,
                    name: 'COCA COLA',
                    price: 200,
                    image: 'https://i.pinimg.com/736x/86/d8/9a/86d89aececbf4358d73d828be06bf5b5.jpg',
                    description: 'a flavor profile built on a blend of caramel sweetness, citrus oils '

                },
                {
                    id: 5,
                    name: 'LEMON JUICE',
                    price: 250,
                    image: 'https://i.pinimg.com/736x/b2/fd/29/b2fd29e9ba90752c1f60c120cb700348.jpg',
                    description: 'the acidic, sour liquid obtained by squeezing the endocarp of lemons.'

                },
                {
                    id: 6,
                    name: 'SPRITE',
                    price: 200,
                    image: 'https://i.pinimg.com/736x/fa/8d/7c/fa8d7c7b3c7fef50a044e2dcbb018a0d.jpg',
                    description: 'A clear, caffeine-free, lemon-lime-flavored soft drink '

                },
                {
                    id: 7,
                    name: 'BLUE LEMONADE',
                    price: 280,
                    image: 'https://i.pinimg.com/736x/b6/a5/16/b6a51678cec52d7fc060cbcf21361565.jpg',
                    description: 'characterized by its bright blue color and refreshing lemon flavor.'

                },
                {
                    id: 8,
                    name: 'ORANGE JUICE',
                    price: 250,
                    image: 'https://i.pinimg.com/736x/dd/e6/c1/dde6c19f17fa56e1fafaa35e020b0756.jpg',
                    description: 'a liquid extract produced by squeezing or reaming the fruit of the orange tree'

                },

            ],

            desserts: [
                {
                    id: 1,
                    name: 'LECHE FLAN',
                    price: 220,
                    image: 'https://i.pinimg.com/736x/e8/50/08/e8500899188333b4f9868dbe561fa80f.jpg',
                    description: 'a rich, dense, and sweet Filipino caramel custard dessert.'

                },
                {
                    id: 2,
                    name: 'BELGIAN WAFFLE',
                    price: 300,
                    image: 'https://i.pinimg.com/736x/48/2a/57/482a5709b40093d1d5ffc035a5386f5e.jpg',
                    description: 'leavened waffle featuring a light, airy interior, a crispy exterior'

                },
                {
                    id: 3,
                    name: 'MANGO CREAM CREPES',
                    price: 210,
                    image: 'https://i.pinimg.com/736x/ff/af/7c/ffaf7ce0e5b1617ca8ee863b36b984a8.jpg',
                    description: 'it filled with sweet vanilla-scented whipped cream and fresh mango chunks.'

                },
                {
                    id: 4,
                    name: 'JAPANESE PANCAKE',
                    price: 200,
                    image: 'https://i.pinimg.com/736x/a9/fe/75/a9fe75a4c0f2a123abac66dbb71085ec.jpg',
                    description: 'lighter and airier than traditional Western pancakes.'

                },
                {
                    id: 5,
                    name: 'BISCOFF CHEESECAKE',
                    price: 250,
                    image: 'https://i.pinimg.com/1200x/63/dc/b2/63dcb2aeda165413627206d7c389f345.jpg',
                    description: 'spiced flavor of Lotus Biscoff cookies and cookie butter.'

                },
                {
                    id: 6,
                    name: 'OREO MILKSHAKE',
                    price: 200,
                    image: 'https://i.pinimg.com/736x/db/4f/6f/db4f6fe576135014305f0547721362ff.jpg',
                    description: 'made by blending milk, ice cream, and crushed Oreo cookies.'

                },
                {
                    id: 7,
                    name: 'ICECREAM',
                    price: 280,
                    image: 'https://i.pinimg.com/736x/8e/97/55/8e975567149d3288383e559f8c819668.jpg',
                    description: 'made from a mixture of milk, cream, sugar, and flavorings '

                },
                {
                    id: 8,
                    name: 'MANGO FLOAT',
                    price: 250,
                    image: 'https://i.pinimg.com/1200x/8b/96/9e/8b969e362ba0e79d37468e4fa40eee93.jpg',
                    description: 'crisp graham crackers, sweetened whipped cream, and ripe mango slices.'

                },

            ],


        }
    }, methods: {

    }
}

</script>


<template>


    <!-- MEALS CARDS -->
    <div class="px-10 py-5 bg-black ">

        <div class="flex justify-between items-center px-48">
            <h1 class="text-3xl font-bold italic text-center text-white m-10">Meals Menu :</h1>
            <p class="text-2xl text-white ">X</p>
        </div>
        <section class="grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-4 px-45">

            <div v-for="meal in meals" :key="meal.id"
                class="food-card relative rounded-[28px] border border-stone-100 bg-white p-5 shadow-lg" :class="index === 1
                    ? 'bg-amber-400'
                    : ''">

                <!-- Food Image -->
                <div class="relative mb-5 flex justify-center pt-2">

                    <span
                        class="absolute left-0 top-0 z-10 rounded-full bg-rose-500 px-3 py-1 text-xs font-bold text-white shadow">
                        Popular
                    </span>

                    <img :src="meal.image" :alt="meal.name"
                        class="food-image h-40 w-40 rounded-full object-cover shadow-xl ring-4" :class="index === 1
                            ? 'ring-white/50'
                            : 'ring-stone-100'">

                </div>

                <!-- Food Name -->
                <h3 class="min-h-[52px] text-center text-xl font-extrabold" :class="index === 1
                    ? 'text-white'
                    : 'text-stone-900'">
                    {{ meal.name }}
                </h3>

                <p>{{ meal.description }}</p>


                <!-- Price and Add Button -->
                <div class="mt-5 flex items-center justify-between">

                    <div>
                        <p class="text-2xl font-extrabold" :class="index === 1
                            ? 'text-white'
                            : 'text-stone-900'">
                            ₱{{ meal.price }}
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

    <!-- SNACKS CARDS -->
    <div class="px-10 py-5 bg-black ">

        <div class="flex justify-between items-center px-48">
            <h1 class="text-3xl font-bold italic text-center text-white m-10">Snacks Menu :</h1>
            <p class="text-2xl text-white ">X</p>
        </div>
        <section class="grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-4 px-45">

            <div v-for="snack in snacks" :key="snack.id"
                class="food-card relative rounded-[28px] border border-stone-100 bg-white p-5 shadow-lg" :class="index === 1
                    ? 'bg-amber-400'
                    : ''">

                <!-- Food Image -->
                <div class="relative mb-5 flex justify-center pt-2">

                    <span
                        class="absolute left-0 top-0 z-10 rounded-full bg-rose-500 px-3 py-1 text-xs font-bold text-white shadow">
                        Popular
                    </span>

                    <img :src="snack.image" :alt="snack.name"
                        class="food-image h-40 w-40 rounded-full object-cover shadow-xl ring-4" :class="index === 1
                            ? 'ring-white/50'
                            : 'ring-stone-100'">

                </div>

                <!-- Food Name -->
                <h3 class="min-h-[52px] text-center text-xl font-extrabold" :class="index === 1
                    ? 'text-white'
                    : 'text-stone-900'">
                    {{ snack.name }}
                </h3>
                <p>{{ snack.description }}</p>


                <!-- Price and Add Button -->
                <div class="mt-5 flex items-center justify-between">

                    <div>
                        <p class="text-2xl font-extrabold" :class="index === 1
                            ? 'text-white'
                            : 'text-stone-900'">
                            ₱{{ snack.price }}
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


    <!-- DRINKS CARDS -->
    <div class="px-10 py-5 bg-black ">

        <div class="flex justify-between items-center px-48">
            <h1 class="text-3xl font-bold italic text-center text-white m-10">Drinks Menu :</h1>
            <p class="text-2xl text-white ">X</p>
        </div>
        <section class="grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-4 px-45">

            <div v-for="drink in drinks" :key="drink.id"
                class="food-card relative rounded-[28px] border border-stone-100 bg-white p-5 shadow-lg" :class="index === 1
                    ? 'bg-amber-400'
                    : ''">

                <!-- Food Image -->
                <div class="relative mb-5 flex justify-center pt-2">

                    <span
                        class="absolute left-0 top-0 z-10 rounded-full bg-rose-500 px-3 py-1 text-xs font-bold text-white shadow">
                        Popular
                    </span>

                    <img :src="drink.image" :alt="drink.name"
                        class="food-image h-40 w-40 rounded-full object-cover shadow-xl ring-4" :class="index === 1
                            ? 'ring-white/50'
                            : 'ring-stone-100'">

                </div>

                <!-- Food Name -->
                <h3 class="min-h-[52px] text-center text-xl font-extrabold" :class="index === 1
                    ? 'text-white'
                    : 'text-stone-900'">
                    {{ drink.name }}
                </h3>

                <p>{{ drink.description }}</p>


                <!-- Price and Add Button -->
                <div class="mt-5 flex items-center justify-between">

                    <div>
                        <p class="text-2xl font-extrabold" :class="index === 1
                            ? 'text-white'
                            : 'text-stone-900'">
                            ₱{{ drink.price }}
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

    <!-- DESSERT CARDS -->
    <div class="px-10 py-5 bg-black ">

        <div class="flex justify-between items-center px-48">
            <h1 class="text-3xl font-bold italic text-center text-white m-10">Dessert Menu :</h1>
            <p class="text-2xl text-white ">X</p>
        </div>
        <section class="grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-4 px-45">

            <div v-for="dessert in desserts" :key="dessert.id"
                class="food-card relative rounded-[28px] border border-stone-100 bg-white p-5 shadow-lg" :class="index === 1
                    ? 'bg-amber-400'
                    : ''">

                <!-- Food Image -->
                <div class="relative mb-5 flex justify-center pt-2">

                    <span
                        class="absolute left-0 top-0 z-10 rounded-full bg-rose-500 px-3 py-1 text-xs font-bold text-white shadow">
                        Popular
                    </span>

                    <img :src="dessert.image" :alt="dessert.name"
                        class="food-image h-40 w-40 rounded-full object-cover shadow-xl ring-4" :class="index === 1
                            ? 'ring-white/50'
                            : 'ring-stone-100'">

                </div>

                <!-- Food Name -->
                <h3 class="min-h-[52px] text-center text-xl font-extrabold" :class="index === 1
                    ? 'text-white'
                    : 'text-stone-900'">
                    {{ dessert.name }}
                </h3>

                <p>{{ dessert.description }}</p>


                <!-- Price and Add Button -->
                <div class="mt-5 flex items-center justify-between">

                    <div>
                        <p class="text-2xl font-extrabold" :class="index === 1
                            ? 'text-white'
                            : 'text-stone-900'">
                            ₱{{ dessert.price }}
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