<script>

export default {
    emits: ['GoTo',],
    data() {
        return {

        }
    }, methods: {
        navi(page) {
            this.$emit('GoTo', page);
        }
    }
}

</script>

<template>

    <div class=" bg-zinc-200 w-full h-80 flex justify-center items-center">

        <footer class="flex flex-col space-y-8">

            <h1 class="text-yellow-500 font-bold text-xl text-center">Silingan<span class="text-black">Foods</span></h1>

            <nav class="flex justify-center flex-wrap gap-6 text-gray-500 font-medium">
                <p @click="navi('Home')" class="hover:text-gray-900 cursor-pointer">Home</p>
                <p @click="navi('Menu')" class="hover:text-gray-900 cursor-pointer">Menu</p>
                <p @click="navi('About')" class="hover:text-gray-900 cursor-pointer">About</p>
                <p @click="navi('Contact')" class="hover:text-gray-900 cursor-pointer">Contact</p>
            </nav>

            <div class="flex justify-center space-x-5">
                <a href="https://facebook.com" target="_blank" rel="noopener noreferrer">
                    <img src="https://img.icons8.com/fluent/30/000000/facebook-new.png" />
                </a>
                <a href="https://instagram.com" target="_blank" rel="noopener noreferrer">
                    <img src="https://img.icons8.com/fluent/30/000000/instagram-new.png" />
                </a>
                <a href="https://messenger.com" target="_blank" rel="noopener noreferrer">
                    <img src="https://img.icons8.com/fluent/30/000000/facebook-messenger--v2.png" />
                </a>
                <a href="https://www.foodpanda.ph/" target="_blank" rel="noopener noreferrer">
                    <img src="../assets/foodpanda.png" class="w-8" />
                </a>
                <a href="https://www.grab.com/ph/food/" target="_blank" rel="noopener noreferrer">
                    <img src="https://images.seeklogo.com/logo-png/33/2/grab-logo-png_seeklogo-332942.png"
                        class="w-8" />
                </a>
            </div>
            <p class="text-center text-gray-700 font-medium">&copy; 2026 Silingan Ltd. All rights reservered.</p>
        </footer>
    </div>
</template>