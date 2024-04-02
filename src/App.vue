<script setup>
import { ref, computed } from 'vue'
import PreLoader from './components/PreLoader.vue'
import Header from './components/Header.vue'
import HomePage from './components/HomePage.vue'
import AboutUs from './components/AboutUs.vue'
import MakeAppointment from './components/MakeAppointment.vue'
import NotFound from './components/NotFound.vue'
import Footer from './components/Footer.vue'

const routes = {
  '/': HomePage,
  '/about': AboutUs,
  '/appointment' : MakeAppointment
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] || NotFound
})
</script>

<template>
  <PreLoader />
  <Header />
  <div class="main-container">
    <component :is="currentView" />
  </div>
  <Footer />
</template>

<style scoped>
.main-container {
  width: 100%;
}
</style>


