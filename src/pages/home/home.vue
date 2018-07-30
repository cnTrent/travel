<template>
    <div class="home">
       <home-header></home-header>
       <home-swiper :list="swiperList"></home-swiper>
       <home-icons :list="iconList"></home-icons>
       <home-recommend :list="recommendList"></home-recommend>
       <home-weekend :list="weekendList"></home-weekend>
    </div>
</template>

<script>
import homeHeader from './components/header'
import homeSwiper from './components/Swiper'
import homeIcons from './components/icons'
import homeRecommend from './components/Recommend'
import homeWeekend from './components/Weekend'
//引入axios
import axios from 'axios'
export default {
    name:"home",
    components:{
        homeHeader,
        homeSwiper,
        homeIcons,
        homeRecommend,
        homeWeekend
    },
    data(){
        return{
            swiperList: [],
            iconList:[],
            recommendList:[],
            weekendList:[]
        }
    },
    //methods 将被混入到 Vue 实例中。可以直接通过 VM 实例访问这些方法，
    //或者在指令表达式中使用。方法中的 this 自动绑定为 Vue 实例
    methods:{
        getHomeInfo(){
            axios.get('/api/index.json')
            .then(this.getHomeInfoSucc)
        },
        getHomeInfoSucc(res){
            res = res.data
            if(res.ret){
                const data= res.data
                this.swiperList=data.swiperList
                this.iconList=data.iconList
                this.recommendList=data.recommendList 
                this.weekendList=data.weekendList
            }
             console.log(this.swiperList)
        }
    },
    //mounted是页面挂载完成的方法
    mounted(){
        this.getHomeInfo()
    }
}
</script>

<style>

</style>
