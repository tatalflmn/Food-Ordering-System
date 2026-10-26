<script>
import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'
import About from './components/About.vue'
import Contact from './components/Contact.vue'
import Cardlist from './components/Cardlist.vue'
import FoodCard from './components/FoodCard.vue'
import Footer from './components/Footer.vue'
import Menupage from './components/Menupage.vue'

export default {
  components: {
    Navbar,
    Home,
    About,
    Contact,
    Cardlist,
    FoodCard,
    Footer,
    Menupage,
  },

  data() {
    return {
      currentPage: 'Home',
      cart: false,
    }
  }, methods: {
    section(p){
      this.currentPage = p;
    },
    navScroll(){
      window.scrollTo({
        top:0,
        behavior: 'smooth'
      })
    },
    openCartModal(i) {
      this.cart = i
    },
    closeModal(i) {
      this.cart = i;
    },
  }
}
</script>

<template>
  <Navbar @click="navScroll" @GoTo="section" @showCartModal="openCartModal"/>
  <Home v-if="currentPage === 'Home'"/>
  <About v-if="currentPage === 'About'" @GoTo="section"/>
  <Contact v-if="currentPage === 'Contact'"/>
  <Cardlist v-if="cart === true" @close="closeModal"/>
  <FoodCard/>
  <Footer/>
  <Menupage v-if="currentPage === 'Menu'"/>
</template>
