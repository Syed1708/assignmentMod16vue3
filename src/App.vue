<script setup>
import {ref} from 'vue'
// import SlotComponent from './components/SlotComponent.vue'
import Header from './components/Header.vue';
import HeroComponent from './components/HeroComponent.vue'
import SliderComponent from './components/SliderComponent.vue';
import FeaturesComponent from './components/FeaturesComponent.vue'
import CallToActionComponent from './components/CallToActionComponent.vue'
import ProtfolioComponent from './components/ProtfolioComponent.vue'
import Footer from './components/Footer.vue'


</script>

<template>

  <Header/>


<HeroComponent/>
<SliderComponent/>

<CallToActionComponent/>
<FeaturesComponent/>
<ProtfolioComponent/>



<Footer/>

</template>

<style scoped>

</style>
