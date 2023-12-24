<template>

  <div >
    <template v-if="item">
      <van-image
        width="100vw"
        fit="cover"
        :src="item.thumb"
      />
      <div class="container">
        <MTitle>{{ item.title }}</MTitle>
        
        <Highlight class="desc" :keywords="keywords" :source-string="item.desc" />

        <MTitle>Цена: {{ item.price }} руб.</MTitle>
      </div>
      

      

      <MSlider  class="MSlider" :images="item.images.map(({ img }) => img)" />


      <section class="section form">
        <MTitle class="container"> Связаться с нами </MTitle>
        <MForm />
      </section>
    </template>



    
  </div>
   
</template>

<script>
import { items } from '~/data.js'
import { Image as VanImage } from 'vant';
import MTitle from '~/ui/MTitle.vue'
import { Highlight } from 'vant';
import MSlider from '~/ui/MSlider.vue'
import MForm from '~/components/MForm.vue'
export default {
    data(){
        const { id } = this.$route.params

        const item = items.find((item) => item.id == id)
        return {
            item: item || null,

            keywords: ['лучше и увереннее', 'Существует']
        }
        
    },  

    components: {
      VanImage,
      MTitle,
      Highlight,
      MSlider,
      MForm
    }
  
}
</script>

<style scoped >
.desc{
  text-align: justify;
  line-height: 26px;
}
.MSlider{
  margin: 30px 0px 0px;
}
</style>