<script>
export default {
    name: 'Cardlist',
    props: {
        cart: {
            type: Array,
            default: () => []
        }
    },
    emits: ['close', 'update-quantity', 'remove-item', 'clear-cart', 'submit-order'],
    data() {
        return {
            isCheckingOut: false,
            showSummaryModal: false,   // Controls the order summary modal
            showSuccessModal: false,   // Controls the order successful modal
            deliveryFee: 50,           // Fixed delivery fee amount
            form: {
                name: '',
                address: '',
                paymentMethod: 'Cash on Delivery'
            }
        }
    },
    computed: {
        totalItems() {
            return this.cart.reduce((total, item) => total + item.quantity, 0);
        },
        cartSubtotal() {
            return this.cart.reduce((total, item) => total + (item.price * item.quantity), 0);
        },
        grandTotal() {
            return this.cartSubtotal + this.deliveryFee;
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
        proceedToCheckout() {
            this.isCheckingOut = true;
        },
        backToCart() {
            this.isCheckingOut = false;
        },
        handleCheckoutClick() {
            if (!this.form.name.trim() || !this.form.address.trim()) {
                alert('Please enter your name and delivery address.');
                return;
            }
            this.showSummaryModal = true;
        },
        // Triggered when clicking "Place Order" on the summary modal
        placeOrder() {
            // Close summary modal and open success modal
            this.showSummaryModal = false;
            this.showSuccessModal = true;
            
            // Submit order details to parent
            this.$emit('submit-order', { 
                ...this.form, 
                items: this.cart, 
                subtotal: this.cartSubtotal, 
                deliveryFee: this.deliveryFee, 
                grandTotal: this.grandTotal 
            });
        },
        // Triggered when closing/finishing the success modal
        finishOrder() {
            this.$emit('clear-cart');
            
            // Reset all states
            this.showSuccessModal = false;
            this.isCheckingOut = false;
            this.form.name = '';
            this.form.address = '';
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
                        {{ isCheckingOut ? 'CHECKOUT' : 'CART LIST' }}
                    </h2>
                    <p class="mt-1 text-sm text-purple-200">
                        {{ isCheckingOut ? 'Enter your details' : `${totalItems} item` + (totalItems !== 1 ? 's' : '') }}
                    </p>
                </div>
                <div class="flex justify-end">
                    <button @click="xbnt" class="text-2xl cursor-pointer text-white font-bold bg-transparent border-0">X</button>
                </div>
            </div>

            <!-- Body (Switches between Cart Items and Checkout Form) -->
            <div class="overflow-y-auto p-4 sm:p-6 flex-1">
                
                <!-- CHECKOUT FORM -->
                <div v-if="isCheckingOut" class="space-y-4">
                    <div class="bg-white p-4 rounded-2xl shadow-md space-y-3">
                        <h3 class="font-bold text-gray-800 text-lg border-b pb-2">Customer Information</h3>
                        
                        <div>
                            <label class="block text-xs font-bold text-gray-600 mb-1">Full Name</label>
                            <input v-model="form.name" type="text" placeholder="e.g., Juan Dela Cruz" class="w-full rounded-lg border border-gray-300 p-2.5 text-sm focus:outline-none focus:ring-2 focus:ring-yellow-500">
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-gray-600 mb-1">Delivery Address</label>
                            <textarea v-model="form.address" rows="3" placeholder="Street, Barangay, City" class="w-full rounded-lg border border-gray-300 p-2.5 text-sm focus:outline-none focus:ring-2 focus:ring-yellow-500"></textarea>
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-gray-600 mb-1">Payment Method</label>
                            <select v-model="form.paymentMethod" class="w-full rounded-lg border border-gray-300 p-2.5 text-sm bg-white focus:outline-none focus:ring-2 focus:ring-yellow-500">
                                <option value="Cash on Delivery">Cash on Delivery (COD)</option>
                                <option value="GCash">GCash</option>
                                <option value="Credit/Debit Card">Credit / Debit Card</option>
                            </select>
                        </div>
                    </div>
                </div>

                <!-- CART ITEMS & EMPTY STATE -->
                <template v-else>
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

                    <div v-else class="space-y-4">
                        <div v-for="item in cart" :key="item.id" class="flex flex-col gap-4 rounded-2xl bg-white p-4 shadow-md sm:flex-row sm:items-center justify-between">
                            <div class="flex items-center gap-3 min-w-0 flex-1">
                                <img :src="item.image" :alt="item.name" class="w-16 h-16 rounded-full object-cover shadow-md flex-shrink-0">
                                <div class="min-w-0 flex-1">
                                    <h3 class="font-bold text-gray-800 text-sm truncate">
                                        {{ item.name }}
                                    </h3>
                                    <p class="mt-1 font-semibold text-yellow-600 text-sm">
                                        ₱{{ item.price }}
                                    </p>
                                    <div class="flex items-center gap-2 mt-2">
                                        <button @click="decrement(item)" class="rounded-lg bg-gray-200 px-2 py-0.5 text-base font-bold shadow transition hover:bg-pink-200 cursor-pointer">−</button>
                                        <span class="min-w-6 text-center font-bold text-sm">{{ item.quantity }}</span>
                                        <button @click="increment(item)" class="rounded-lg bg-gray-200 px-2 py-0.5 text-base font-bold hover:bg-pink-200 cursor-pointer">+</button>
                                    </div>
                                </div>
                            </div>
                            <button @click="removeItem(item.id)" class="rounded-xl text-red-500 text-center font-bold transition hover:scale-105 duration-100 cursor-pointer bg-transparent border-0 self-end sm:self-center text-sm">
                                Remove
                            </button>
                        </div>
                    </div>
                </template>
            </div>

            <!-- Footer -->
            <div class="border-t bg-black p-5 text-white sm:p-6">
                <div class="flex flex-col gap-4">
                    <div class="flex justify-between items-center">
                        <p class="text-xl font-black">
                            Total: ₱{{ isCheckingOut ? grandTotal : cartSubtotal }}
                        </p>
                    </div>

                    <div class="flex gap-2">
                        <!-- Buttons when in Checkout Form view -->
                        <template v-if="isCheckingOut">
                            <button @click="handleCheckoutClick" class="flex-1 rounded-xl bg-yellow-500 px-4 py-3 font-bold text-white shadow-lg transition hover:bg-yellow-600 cursor-pointer">
                                Confirm Order
                            </button>
                            <button @click="backToCart" class="rounded-xl bg-gray-300 text-black px-4 py-3 font-bold transition hover:bg-gray-400 cursor-pointer">
                                Back
                            </button>
                        </template>

                        <!-- Buttons when viewing Cart items -->
                        <template v-else>
                            <button @click="proceedToCheckout" :disabled="cart.length === 0" class="flex-1 rounded-xl bg-yellow-500 px-4 py-3 font-bold text-white shadow-lg transition hover:bg-yellow-600 cursor-pointer disabled:opacity-50">
                                Pay Now
                            </button>
                            <button @click="clearCart" :disabled="cart.length === 0" class="rounded-xl text-black bg-gray-300 px-4 py-3 font-bold transition hover:text-white hover:bg-black cursor-pointer disabled:opacity-50">
                                Clear Cart
                            </button>
                        </template>
                    </div>
                </div>
            </div>

        </div>

        <!-- ORDER SUMMARY SUB-MODAL -->
        <div v-if="showSummaryModal" class="fixed inset-0 z-[1000] flex items-center justify-center bg-black/60 p-4">
            <div class="w-full max-w-sm rounded-2xl bg-white p-6 shadow-2xl space-y-4">
                <h3 class="text-xl font-black text-gray-900 border-b pb-2">Order Summary</h3>
                
                <div class="space-y-2 text-sm text-gray-700">
                    <div class="flex justify-between">
                        <span>Products Subtotal:</span>
                        <span class="font-bold">₱{{ cartSubtotal }}</span>
                    </div>
                    <div class="flex justify-between">
                        <span>Delivery Fee:</span>
                        <span class="font-bold">₱{{ deliveryFee }}</span>
                    </div>
                    <div class="flex justify-between border-t pt-2 text-base font-black text-black">
                        <span>Grand Total:</span>
                        <span class="text-yellow-600">₱{{ grandTotal }}</span>
                    </div>
                </div>

                <div class="flex gap-2 pt-2">
                    <button @click="placeOrder" class="flex-1 rounded-xl bg-yellow-500 px-4 py-3 font-bold text-white shadow transition hover:bg-yellow-600 cursor-pointer">
                        Place Order
                    </button>
                    <button @click="showSummaryModal = false" class="rounded-xl bg-gray-200 px-4 py-3 font-bold text-black transition hover:bg-gray-300 cursor-pointer">
                        Cancel
                    </button>
                </div>
            </div>
        </div>

        <!-- ORDER SUCCESSFUL MODAL -->
        <div v-if="showSuccessModal" class="fixed inset-0 z-[1001] flex items-center justify-center bg-black/60 p-4">
            <div class="w-full max-w-sm rounded-2xl bg-white p-6 text-center shadow-2xl space-y-4">
                <div class="mx-auto grid h-16 w-16 place-items-center rounded-full bg-green-100 text-3xl text-green-600 font-bold">
                    ✓
                </div>
                <div>
                    <h3 class="text-2xl font-black text-gray-900">Order Successful!</h3>
                    <p class="mt-1 text-sm text-gray-600">
                        Thank you for your purchase. Your order has been placed successfully.
                    </p>
                </div>
                <button @click="finishOrder" class="w-full rounded-xl bg-yellow-500 px-4 py-3 font-bold text-white shadow transition hover:bg-yellow-600 cursor-pointer">
                    Done
                </button>
            </div>
        </div>

    </div>
</template>