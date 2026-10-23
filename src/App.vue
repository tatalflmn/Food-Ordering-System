<script>
import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'

export default {
  components: {
    Navbar,
    Home,
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
</template>
