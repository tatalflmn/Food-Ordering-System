<script>
export default {
    emits: ['close'],
    data() {
        return {

        }

    },
    methods: {
        xbnt(i) {
            this.$emit('close', i);
        },
    }
}
</script>
<template>
    <div class="inset-0 z-999 flex items-center h-screen justify-end top-0 fixed">

        <div
            class="relative flex justify-between h-screen w-full max-w-sm flex-col overflow-hidden  rounded-xl bg-gray-200 shadow-2xl">

            <div class="flex items-center justify-between bg-black/30 px-5 py-4 text-white sm:px-7">


                <div>

                    <h2 class="text-2xl font-black sm:text-3xl">
                        CART LIST
                    </h2>

                    <p class="mt-1 text-sm text-purple-100">
                        <!-- {{cart.reduce((total, item) => total + item.quantity, 0)}}
                        item<span v-if="cart.reduce((total, item) => total + item.quantity, 0) !== 1">s</span> -->
                    </p>

                </div>
                <div class="flex justify-end">
                    <button @click="xbnt(false)" class="text-2xl cursor-pointer text-white font-bold">X</button>
                </div>
            </div>

            <div class="overflow-y-auto p-4 sm:p-6">

                <div class="rounded-2xl bg-black/0 p-8 text-center sm:p-12">

                    <div class="mx-auto grid h-20 w-20 place-items-center rounded-full bg-purple-100 text-4xl">
                        🛒
                    </div>

                    <h3 class="mt-5 text-2xl font-bold">
                        Your cart is empty
                    </h3>

                    <p class="mt-2 text-yellow-600">
                        Add some products to your cart and they will appear here.
                    </p>

                </div>

                <div class="space-y-4">

                    <div class="flex flex-col gap-4 rounded-2xl bg-black/0  p-4 shadow-md sm:flex-row sm:items-center">


                        <div class="min-w-0 flex-1">

                            <h3 class="font-bold text-yellow-600">
                                <!-- {{ item.name }} -->
                            </h3>

                            <p class="mt-1 font-semibold text-yellow-600">
                                <!-- ₱{{ item.price }} -->
                            </p>

                            <div class="flex items-center gap-2 ">

                                <button
                                    class="rounded-lg bg-black/20 px-3 py-1 text-lg font-bold  shadow transition hover:bg-pink-200">
                                    −
                                </button>

                                <span class="min-w-8 text-center font-bold">
                                    <!-- {{ item.quantity }} -->
                                </span>

                                <button
                                    class="rounded-lg bg-black/20 px-3 py-1 text-lg font-bold  hover:bg-pink-200">
                                    +
                                </button>

                            </div>

                        </div>
                        <button
                            class="rounded-xl text-red-500 text-center  font-bold transition hover:scale-103 duration-100">
                            Remove
                        </button>

                    </div>

                </div>

            </div>

            <div class="border-t bg-black/20 p-5 text-white sm:p-6">

                <div class="flex flex-col gap-4 sm:flex-row sm:items-center sm:justify-between">

                    <p class="text-xl font-black">
                        <!-- Total: ₱{{ cartTotal }} -->
                    </p>

                    <div class="flex gap-2">

                        <button @click="payNow"
                            class="rounded-xl bg-yellow-500 px-5 py-3 font-bold text-white shadow-lg transition hover:bg-yellow-600 cursor-pointer">
                            Pay Now
                        </button>

                        <button @click="clearCart"
                            class="rounded-xl text-black px-5 py-3 font-bold  transition hover:text-white hover:bg-black cursor-pointer">
                            Clear Cart
                        </button>

                    </div>

                </div>

            </div>

        </div>

    </div>

</template>