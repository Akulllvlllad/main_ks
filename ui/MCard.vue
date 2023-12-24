<template>
    <NuxtLink  :to=" '/' + paramCard.id">
        <Card  v-bind="paramCard" />
    </NuxtLink>

</template>

<script>


import { Card, Button, showImagePreview} from 'vant';
export default {
    name: 'MCard',
    props: {
        options: { default: () => {}, type: Object },
    
    },
    computed: {
        paramCard(){
            return {
                currency: "",
                price: "2300.00",
                title: "Стиль",
                desc: "Стиль нижнего белья непременно должен гармонировать с общим стилем женщины. Он формирует настроение, позволяет чувствовать себя лучше и увереннее. Нижнее белье — это один из элементов, формирующих высокую самооценку и помогающий создавать положительный настрой на день. Существует множество видов нижнего белья, и каждый стиль имеет собственные особенности исполнения, передающий особый замысел. ",
                thumb: 'https://i.postimg.cc/523LQBsZ/IMG-20231224-145616-498.jpg',

                ...this.options
            }
        }
    },
    
    methods: {
        onClick(){
            showImagePreview({
            images: this.images.map(({ img }) => img),
            startPosition: 0,
        });
        
        }
    },  
    components: {
        Button,
        Card,

    }
}
</script>

<style>

</style>