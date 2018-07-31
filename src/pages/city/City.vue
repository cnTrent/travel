<template>
    <div class="city">
        <city-header></city-header>
        <city-search></city-search>
        <city-list :cityes='cities' :hot="hotCities"></city-list>
        <city-alphabet :cityes='cities'></city-alphabet>
    </div>
</template>
<script>
import axios from 'axios'
import CityHeader from './components/header'
import CitySearch from './components/search'
import CityList from './components/list'
import CityAlphabet from './components/Alphabet'
export default {
    name:"City",
    components:{
        CityHeader,
        CitySearch,
        CityList,
        CityAlphabet
    },
    data(){
        return{
            cities:{},
            hotCities:[]
        }
    },
    methods:{
        getCityInfo(){
            axios.get('/api/city.json')
            .then(this.handleGetCityInfoSucc)
        },
        handleGetCityInfoSucc(res){
                res = res.data
                if(res.ret&&res.data){
                    const data = res.data
                    this.cities = data.cities
                    this.hotCities = data.hotCities
                    console.log(data.cities)
                }
            }
    },
    mounted(){
        this.getCityInfo()
    }
}
</script>
<style lang="scss" scoped>
</style>
