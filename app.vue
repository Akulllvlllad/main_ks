<template>
    <div class="wrapper">
    
        <NavBar 
            left-text="Назад"
            left-arrow
            @click-left="onClickLeft"
        >
            

            <template #left v-if="data && data.left">
                <h3 v-text="data.left" />
            </template>

            <template #right>
                <a href="https://www.instagram.com/main_4u">
                    <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="30" height="30" viewBox="0 0 50 50">
                        <path d="M 16 3 C 8.8324839 3 3 8.8324839 3 16 L 3 34 C 3 41.167516 8.8324839 47 16 47 L 34 47 C 41.167516 47 47 41.167516 47 34 L 47 16 C 47 8.8324839 41.167516 3 34 3 L 16 3 z M 16 5 L 34 5 C 40.086484 5 45 9.9135161 45 16 L 45 34 C 45 40.086484 40.086484 45 34 45 L 16 45 C 9.9135161 45 5 40.086484 5 34 L 5 16 C 5 9.9135161 9.9135161 5 16 5 z M 37 11 A 2 2 0 0 0 35 13 A 2 2 0 0 0 37 15 A 2 2 0 0 0 39 13 A 2 2 0 0 0 37 11 z M 25 14 C 18.936712 14 14 18.936712 14 25 C 14 31.063288 18.936712 36 25 36 C 31.063288 36 36 31.063288 36 25 C 36 18.936712 31.063288 14 25 14 z M 25 16 C 29.982407 16 34 20.017593 34 25 C 34 29.982407 29.982407 34 25 34 C 20.017593 34 16 29.982407 16 25 C 16 20.017593 20.017593 16 25 16 z"></path>
                    </svg>
                </a>
            </template>
        </NavBar>
        
        <NuxtPage />

        <Tabbar class="Tabbar">
            <TabbarItem icon="home-o">Главная</TabbarItem>
            <TabbarItem icon="share" @click="showShare = true">Поделится</TabbarItem>
            <TabbarItem icon="shopping-cart" @click="showNotify({ type: 'warning', message: 'В разработке' });" >Корзина</TabbarItem>
        </Tabbar>

        <ShareSheet  v-model:show="showShare" :options="options" cancel-text="Закрыть" />
        <Notify />
    </div>
</template>

<script>
import { NavBar } from 'vant';
import { Tabbar, TabbarItem } from 'vant';
import { ShareSheet } from 'vant';
import { showNotify } from 'vant';
import { Notify } from 'vant';
import 'vant/lib/index.css';

export default {
    data(){
        return {
            showShare: false,
            options: [
            {
                name: 'Инстаграм',
                icon: 'https://fastly.jsdelivr.net/npm/@vant/assets/custom-icon-fire.png',
            },
            {
                name: 'Телеграм',
                icon: 'https://fastly.jsdelivr.net/npm/@vant/assets/custom-icon-light.png',
            },
            {
                name: 'Вк',
                icon: 'https://fastly.jsdelivr.net/npm/@vant/assets/custom-icon-water.png',
            },
            ]
        }
    },  
    components: {
        ShareSheet,
        NavBar,
        Tabbar,
        TabbarItem,
        Notify
    },

    methods: {
        onClickLeft(){
            this.$router.replace('/')
        }
    },  
    computed: {
        
        data(){

            const { name } = this.$route

            return [{
                page: 'index',
                left: 'Main_4u'
            }
            
        
        ].find(({ page }) => page === name)
        },
        

    }

}


</script>


<style>
.container{
    margin-inline: 16px;
}

.section{
    padding: 20px 0;
}


.wrapper{
    padding-bottom: 50px;
}


.Tabbar{
    border-top: 1px solid rgba(0, 0, 0, 0.15)
}

.section.form{
  background: var(--van-card-background);
}
</style>