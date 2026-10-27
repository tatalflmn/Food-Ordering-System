<script>
export default {
    emits: ['GoTo', 'showCartModal'],
    data() {
        return {

        }
    }, methods: {
        navi(page) {
            this.$emit('GoTo', page);
        },

        openModal(i) {
            this.$emit('showCartModal', i);
        }
    }
}
</script>

<template>

    <div class="z-99 fixed top-30 left-0">

        <div class=" w-60 ">

            <div class="flex flex-col justify-center items-center w-full h-100 gap-10">
                <img src="../assets/silingan logo.png" alt="" class="w-20">
                

                <div class="text-center flex flex-col gap-10 ">
                    <div class="flex gap-4 items-center">

                        <svg class="fill-white h-8" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 640">
                            <path
                                d="M341.8 72.6C329.5 61.2 310.5 61.2 298.3 72.6L74.3 280.6C64.7 289.6 61.5 303.5 66.3 315.7C71.1 327.9 82.8 336 96 336L112 336L112 512C112 547.3 140.7 576 176 576L464 576C499.3 576 528 547.3 528 512L528 336L544 336C557.2 336 569 327.9 573.8 315.7C578.6 303.5 575.4 289.5 565.8 280.6L341.8 72.6zM304 384L336 384C362.5 384 384 405.5 384 432L384 528L256 528L256 432C256 405.5 277.5 384 304 384z" />
                        </svg>
                        <p @click="navi('Home')"
                            class="text-lg font-semibold text-white hover:scale-103 cursor-pointer">
                            Home</p>
                    </div>

                    <div class="flex gap-4 items-center">
                        <svg class="fill-white h-8" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 640">
                            <path
                                d="M112 448C103.2 448 96 455.2 96 464C96 508.2 131.8 544 176 544L464 544C508.2 544 544 508.2 544 464C544 455.2 536.8 448 528 448L112 448zM96 266C96 278.2 105.9 288 118 288L522 288C534.2 288 544 278.1 544 266C544 248.8 541.4 231.6 533.2 216.5C511 175.7 450.9 96 320 96C189.1 96 129 175.6 106.8 216.5C98.6 231.6 96 248.8 96 266zM64 368C64 385.7 78.3 400 96 400L544 400C561.7 400 576 385.7 576 368C576 350.3 561.7 336 544 336L96 336C78.3 336 64 350.3 64 368zM320 136C333.3 136 344 146.7 344 160C344 173.3 333.3 184 320 184C306.7 184 296 173.3 296 160C296 146.7 306.7 136 320 136zM184 192C184 178.7 194.7 168 208 168C221.3 168 232 178.7 232 192C232 205.3 221.3 216 208 216C194.7 216 184 205.3 184 192zM432 168C445.3 168 456 178.7 456 192C456 205.3 445.3 216 432 216C418.7 216 408 205.3 408 192C408 178.7 418.7 168 432 168z" />
                        </svg>
                        <p @click="navi('Menu')"
                            class="text-lg font-semibold text-white hover:scale-103 cursor-pointer">
                            Menu</p>
                    </div>

                    <div class="flex gap-4 items-center">
                        <svg class="fill-white h-8" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 640">
                            <path
                                d="M320 576C461.4 576 576 461.4 576 320C576 178.6 461.4 64 320 64C178.6 64 64 178.6 64 320C64 461.4 178.6 576 320 576zM288 224C288 206.3 302.3 192 320 192C337.7 192 352 206.3 352 224C352 241.7 337.7 256 320 256C302.3 256 288 241.7 288 224zM280 288L328 288C341.3 288 352 298.7 352 312L352 400L360 400C373.3 400 384 410.7 384 424C384 437.3 373.3 448 360 448L280 448C266.7 448 256 437.3 256 424C256 410.7 266.7 400 280 400L304 400L304 336L280 336C266.7 336 256 325.3 256 312C256 298.7 266.7 288 280 288z" />
                        </svg>

                        <p @click="navi('About')"
                            class="text-lg font-semibold text-white hover:scale-103 cursor-pointer">
                            About</p>
                    </div>

                    <div class="flex gap-4 items-center">
                        <svg class="fill-white h-8" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 640">
                            <path
                                d="M224.2 89C216.3 70.1 195.7 60.1 176.1 65.4L170.6 66.9C106 84.5 50.8 147.1 66.9 223.3C104 398.3 241.7 536 416.7 573.1C493 589.3 555.5 534 573.1 469.4L574.6 463.9C580 444.2 569.9 423.6 551.1 415.8L453.8 375.3C437.3 368.4 418.2 373.2 406.8 387.1L368.2 434.3C297.9 399.4 241.3 341 208.8 269.3L253 233.3C266.9 222 271.6 202.9 264.8 186.3L224.2 89z" />
                        </svg>
                        <p @click="navi('Contact')"
                            class="text-lg bg- font-semibold text-white hover:scale-103 cursor-pointer">
                            Contact</p>
                    </div>

                    <div class="flex items-center">

                        <button @click="openModal(true)"
                            class="border flex gap-2  border-orange-400 text-white hover:bg-orange-500 px-3 py-3 font-semibold rounded-lg cursor-pointer hover:scale-105 duration-300">
                            <svg class="fill-white w-7" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 640">
                                <path
                                    d="M24 48C10.7 48 0 58.7 0 72C0 85.3 10.7 96 24 96L69.3 96C73.2 96 76.5 98.8 77.2 102.6L129.3 388.9C135.5 423.1 165.3 448 200.1 448L456 448C469.3 448 480 437.3 480 424C480 410.7 469.3 400 456 400L200.1 400C188.5 400 178.6 391.7 176.5 380.3L171.4 352L475 352C505.8 352 532.2 330.1 537.9 299.8L568.9 133.9C572.6 114.2 557.5 96 537.4 96L124.7 96L124.3 94C119.5 67.4 96.3 48 69.2 48L24 48zM208 576C234.5 576 256 554.5 256 528C256 501.5 234.5 480 208 480C181.5 480 160 501.5 160 528C160 554.5 181.5 576 208 576zM432 576C458.5 576 480 554.5 480 528C480 501.5 458.5 480 432 480C405.5 480 384 501.5 384 528C384 554.5 405.5 576 432 576z" />
                            </svg>
                        
                            <p
                                class="text-lg bg- font-semibold text-white hover:scale-103 cursor-pointer">
                                My Order</p>
                        </button>
                    </div>
                </div>

            </div>

        </div>
    </div>


</template>