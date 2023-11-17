<script setup>

// import VForArrayComponent from './VForArrayComponent.vue'

import {ref, reactive, onMounted, onUnmounted} from 'vue'



const carouselItems = [
  {
    image: 'https://images.unsplash.com/photo-1682685797769-481b48222adf?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60',
    title: 'First Title',
    caption: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nisi quis recusandae debitis aut aspernatur qui dolorum nemo aliquid adipisci voluptate eius illum, libero aperiam iure possimus numquam ipsa molestias perferendis.'
  },
  {
    image: 'https://images.unsplash.com/photo-1682695794816-7b9da18ed470?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60',
    title: 'Second Title',
    caption: 'Second description'
  },
  {
    image: 'https://images.unsplash.com/photo-1682685797661-9e0c87f59c60?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60',
    title: 'Third Title',
    caption: 'Thired Description'
  },
  {
    image: 'https://plus.unsplash.com/premium_photo-1666963323736-5ee1c16ef19d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60',
    title: 'Fourth Title',
    caption: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nisi quis recusandae debitis aut aspernatur qui dolorum nemo aliquid adipisci voluptate eius illum, libero aperiam iure possimus numquam ipsa molestias perferendis.'
  },

]


const activeIndex = ref(0)

const incrementActiveIndex = () =>{
  if(activeIndex.value == carouselItems.length -1){
    activeIndex.value = 0
  }
  else{
    activeIndex.value++
  }
}

let timerId = null;

const startSlideShow = function(){
  timerId = setInterval(incrementActiveIndex, 2000)
}


const stopSlideShow = function(){
    clearInterval(timerId)
  }
 
  onMounted(() => {
    startSlideShow()
  })

  onUnmounted(() =>{
    stopSlideShow()
  })


</script>

<template>


<div  id="slider">  

  <!-- <VForArrayComponent/> -->

  <div @mouseover="stopSlideShow" @mouseleave="startSlideShow" id="carouselExampleCaptions" class="carousel">    
    
    <ol class="carousel-indicators">
   
      <li class="mr-2" v-for="(items, index) in carouselItems" :key="index" :class="index == activeIndex?'indicatorActive':'indicatorNotactive'" >
      
        {{ index+1 }}
      </li>
      <!-- <li @click="activeIndex = index" v-for="(items, index) in carouselItems" :key="index" :class="index == activeIndex?'active':''"></li> -->
    </ol>
    
    <div class="carousel-inner">     

      <div class="carousel-item " v-for="(carouselitem, index) in carouselItems" :key="index" :class="index == activeIndex?'active':''">           
        <img height="500" :src="carouselitem.image" class="d-block w-100 img img-responsive" :alt="carouselitem.title" >
        <div class="carousel-caption d-none d-md-block">
          <h5>{{ carouselitem.title }}</h5>
          <p>{{ carouselitem.caption }}</p>
        </div>
      </div>  

    </div>    
    <a @click.prevent="0 == activeIndex ? activeIndex = (carouselItems.length) - 1 : activeIndex--" class="carousel-control-prev" href="#" role="button">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Previous</span>
    </a>
    <a @click.prevent="(carouselItems.length) - 1 == activeIndex ? activeIndex = 0 : activeIndex++" class="carousel-control-next" href="#" role="button">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">Next</span>
    </a>


    </div>

</div>





</template>

<style scoped>
 
.indicatorActive{
  color: rgb(21, 228, 100);

}

.indicatorNotactive{
  color: rgb(119, 119, 119);
}

.carousel-indicators li{
  background-color: #250303;
  display: inline-block;
  height: auto;
  width: 20px;
}
</style>
