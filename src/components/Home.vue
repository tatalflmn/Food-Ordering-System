<script>
export default {
  emits: ['GoTo'],
  data() {
    return {

    }
  },
  methods: {
    navi(page) {
      this.$emit('GoTo', page);
    },
  }
}
</script>

<template>

  <div
    class="relative w-full min-h-screen flex flex-col justify-center items-center text-center px-4 sm:px-6 lg:px-16 py-16 sm:py-20 md:py-32 overflow-hidden">
    <!-- Background Image -->

    <img class="absolute inset-0 w-full h-full object-cover object-center"
      src="https://plus.unsplash.com/premium_photo-1695762436987-1cf827e5f1dd?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NTl8fGJ1cmdlcmFpfGVufDB8MHwwfHx8MA%3D%3D"
      alt="">

    <div class="absolute inset-0 bg-black opacity-50"></div>

    <!-- Content -->
    <div class="relative z-10 text-white w-full max-w-2xl mx-auto mt-0 sm:mt-10 md:mt-16 pl-0 sm:pl-4 md:pl-10">
      <h1 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold leading-tight">
        Order Bright, Eat <br> Right!
      </h1>
      <p class="mt-4 text-base sm:text-lg md:text-xl">
        Make your day awesome with our food delivery.
      </p>
      <div class="mt-6">
        <p @click="navi('Menu')"
          class="group px-5 sm:px-6 py-3 cursor-pointer bg-orange-400 hover:bg-orange-500 rounded-lg text-base sm:text-lg font-semibold transition inline-flex items-center">
          Order Now
          <i class="fa-solid fa-arrow-right ml-2 transition-transform group-hover:translate-x-1"></i>
        </p>
      </div>

    </div>
  </div>

</template>