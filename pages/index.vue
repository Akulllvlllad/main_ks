<template>
  <MSlider :images="slider.map(({ img }) => img)" />
  
  <section class="section">
    <MTitle class="container"> Наши товары </MTitle>
    <div class="content">
      <MCard v-for="item of items" :key="item.id" :options="item"/>
    </div>
  </section>



  <section class="section form">
    <MTitle class="container"> Связаться с нами </MTitle>
    <MForm />
  </section>
  


</template>

<script>

import MForm from '~/components/MForm.vue'
import MCard from '~/ui/MCard.vue'
import MTitle from '~/ui/MTitle.vue'
import MSlider from '~/ui/MSlider.vue'

import { items } from '~/data.js'

export default {
  name: 'App',
  data(){
    return {
      items,

      slider: [
        {img: 'https://i.postimg.cc/523LQBsZ/IMG-20231224-145616-498.jpg'},
        {img: 'https://i.postimg.cc/sxh5MbLc/IMG-20231224-145616-782.jpg'},
        {img: 'https://i.postimg.cc/BQ2x49HZ/IMG-20231224-145616-641.jpg'},
        {img: 'https://i.postimg.cc/v8gr26mV/IMG-20231224-145616-788.jpg'},
        {img: 'https://i.postimg.cc/FFMjMsfn/IMG-20231224-145617-159.jpg'},

      ]
    }
  }, 
 
  components: {
    MSlider,
    MTitle,
    MCard,
    MForm,

  }
}
</script>

<style scoped >
.content{
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.swipe{
  height: 300px;
}
.swipe-item{
  width: 100%;
  height: 100%;
  position: relative;
  img {
    position: absolute;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}


</style>