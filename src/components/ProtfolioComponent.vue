<script setup>

const portfolios = [
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
  {
    image: 'https://images.unsplash.com/photo-1507525428034-b723cf961d3e?q=80&w=2073&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    title: '5th Title',
    caption: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nisi quis recusandae debitis aut aspernatur qui dolorum nemo aliquid adipisci voluptate eius illum, libero aperiam iure possimus numquam ipsa molestias perferendis.'
  },
  {
    image: 'https://images.unsplash.com/photo-1507187632231-5beb21a654a2?q=80&w=2101&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
    title: '6th Title',
    caption: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Nisi quis recusandae debitis aut aspernatur qui dolorum nemo aliquid adipisci voluptate eius illum, libero aperiam iure possimus numquam ipsa molestias perferendis.'
  },

]

</script>

<template>
        <!-- Portfolio-->
        <div id="portfolio">
            <div class="container-fluid p-0">
                <h2 class="text-center mt-0">Portfolios</h2>
                <hr class="divider" />
                <div class="row g-0">

                    <div v-for="(portfolio,index) in portfolios" :key="index" class="col-lg-4 col-sm-6">
                        <a class="portfolio-box" :href="portfolio.image" :title="portfolio.title">
                            <img class="img-fluid" :src="portfolio.image" :alt="portfolio.title" />
                            <div class="portfolio-box-caption">
                                <div class="project-name">{{ portfolio.title }}</div>  
                                <div class="project-category text-white-50">{{ portfolio.caption }}</div>
                                 
                            </div>
                        </a>
                    </div>

                    
              
                </div>
            </div>
        </div>
</template>

<style scoped>

</style>