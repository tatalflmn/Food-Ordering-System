<script>
import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'
import About from './components/About.vue'
import Contact from './components/Contact.vue'

export default {
  components: {
    Navbar,
    Home,
    About,
    Contact,
  },

  data() {
    return {
      currentPage: 'Home'
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
    }
  }
}
</script>

<template>
  <Navbar @click="navScroll" @GoTo="section"/>
  <Home v-if="currentPage === 'Home'"/>
  <About v-if="currentPage === 'About'" @GoTo="section"/>
  <Contact v-if="currentPage === 'Contact'"/>
</template>
