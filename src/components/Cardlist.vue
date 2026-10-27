<script>
export default {
    name: 'Cardlist',
    props: {
        cart: {
            type: Array,
            default: () => []
        }
    },
    emits: ['close', 'update-quantity', 'remove-item', 'clear-cart', 'pay'],
    computed: {
        totalItems() {
            return this.cart.reduce((total, item) => total + item.quantity, 0);
        },
        cartTotal() {
            return this.cart.reduce((total, item) => total + (item.price * item.quantity), 0);
        }
    },
    methods: {
        xbnt() {
            this.$emit('close');
        },
        increment(item) {
            this.$emit('update-quantity', { id: item.id, quantity: item.quantity + 1 });
        },
        decrement(item) {
            if (item.quantity > 1) {
                this.$emit('update-quantity', { id: item.id, quantity: item.quantity - 1 });
            } else {
                this.$emit('remove-item', item.id);
            }
        },
        removeItem(id) {
            this.$emit('remove-item', id);
        },
        clearCart() {
            this.$emit('clear-cart');
        },
        payNow() {
            this.$emit('pay');
        }
    }
}
</script>

<template>
    <div class="inset-0 z-[999] flex items-center h-screen justify-end top-0 fixed bg-black/40">
        <div class="relative flex justify-between h-screen w-full max-w-sm flex-col overflow-hidden rounded-l-xl bg-gray-200 shadow-2xl">

            <!-- Header -->
            <div class="flex items-center justify-between bg-black px-5 py-4 text-white sm:px-7">
                <div>
                    <h2 class="text-2xl font-black sm:text-3xl">
                        CART LIST
                    </h2>
                    <p class="mt-1 text-sm text-purple-200">
                        {{ totalItems }} item<span v-if="totalItems !== 1">s</span>
                    </p>
                </div>
                <div class="flex justify-end">
                    <button @click="xbnt" class="text-2xl cursor-pointer text-white font-bold bg-transparent border-0">X</button>
                </div>
            </div>

            <!-- Body -->
            <div class="overflow-y-auto p-4 sm:p-6 flex-1">
                <!-- Empty State -->
                <div v-if="cart.length === 0" class="rounded-2xl bg-black/0 p-8 text-center sm:p-12">
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

                <!-- Item List -->
                <div v-else class="space-y-4">
                    <div v-for="item in cart" :key="item.id" class="flex flex-col gap-4 rounded-2xl bg-white p-4 shadow-md sm:flex-row sm:items-center justify-between">
                        
                        <!-- Product Image & Info Layout -->
                        <div class="flex items-center gap-3 min-w-0 flex-1">
                            <!-- Product Image Added Here -->
                            <img :src="item.image" :alt="item.name" class="w-16 h-16 rounded-full object-cover shadow-md flex-shrink-0">

                            <div class="min-w-0 flex-1">
                                <h3 class="font-bold text-gray-800 text-sm truncate">
                                    {{ item.name }}
                                </h3>
                                <p class="mt-1 font-semibold text-yellow-600 text-sm">
                                    ₱{{ item.price }}
                                </p>

                                <div class="flex items-center gap-2 mt-2">
                                    <button @click="decrement(item)" class="rounded-lg bg-gray-200 px-2 py-0.5 text-base font-bold shadow transition hover:bg-pink-200 cursor-pointer">
                                        −
                                    </button>
                                    <span class="min-w-6 text-center font-bold text-sm">
                                        {{ item.quantity }}
                                    </span>
                                    <button @click="increment(item)" class="rounded-lg bg-gray-200 px-2 py-0.5 text-base font-bold hover:bg-pink-200 cursor-pointer">
                                        +
                                    </button>
                                </div>
                            </div>
                        </div>

                        <button @click="removeItem(item.id)" class="rounded-xl text-red-500 text-center font-bold transition hover:scale-105 duration-100 cursor-pointer bg-transparent border-0 self-end sm:self-center text-sm">
                            Remove
                        </button>
                    </div>
                </div>
            </div>

            <!-- Footer -->
            <div class="border-t bg-black p-5 text-white sm:p-6">
                <div class="flex flex-col gap-4 sm:flex-row sm:items-center sm:justify-between">
                    <p class="text-xl font-black">
                        Total: ₱{{ cartTotal }}
                    </p>

                    <div class="flex gap-2">
                        <button @click="payNow" :disabled="cart.length === 0" class="rounded-xl bg-yellow-500 px-5 py-3 font-bold text-white shadow-lg transition hover:bg-yellow-600 cursor-pointer disabled:opacity-50">
                            Pay Now
                        </button>
                        <button @click="clearCart" :disabled="cart.length === 0" class="rounded-xl text-black bg-gray-300 px-5 py-3 font-bold transition hover:text-white hover:bg-black cursor-pointer disabled:opacity-50">
                            Clear Cart
                        </button>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>