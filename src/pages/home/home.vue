<template>
    <div class="home">
       <home-header></home-header>
       <home-swiper></home-swiper>
    </div>
</template>

<script>
import homeHeader from './components/header'
import homeSwiper from './components/Swiper'
export default {
    name:"home",
    components:{
        homeHeader,
        homeSwiper
    }
}
</script>

<style>

</style>
