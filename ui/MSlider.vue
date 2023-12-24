<template>

  
    <Swipe class="swipe" :autoplay="1200"  >
     
     <SwipeItem  @click="onClick(index)" class="swipe-item" v-for="(item, index) in images" :key="item" >
       
       <img :src="item" />
    
     </SwipeItem>
    
   
   </Swipe>
   
   
</template>

<script>
import { Swipe, SwipeItem, showImagePreview } from 'vant';



export default {
    name: 'MSlider',
    props: {
        images: { default: () => [], type: Array }
    },
   
    methods: {
        onClick(index){
            showImagePreview({
            images: this.images,
            startPosition: index,
            });
        
        }
    },  
    components: {
        Swipe,
        SwipeItem
    }
}
</script>

<style scoped >
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

.section.form{
    background: var(--van-card-background);
}
</style>