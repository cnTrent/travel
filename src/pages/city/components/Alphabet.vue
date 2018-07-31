<template>
    <ul class="list">
        <li class="item" v-for="(item,key) in cityes" :key='key'>{{key}}</li>
    </ul>
</template>
<script>
export default {
    name:"CityAlphabet",
    props:{
        cityes:Object,
    },
}
</script>
<style lang="scss" scoped>
@import "../../../assets/styles/varibles.scss";
.list{
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: absolute;
    top: 1.58rem;
    right:0;
    bottom: 0;
    width: .4rem;
    .item{
        text-align: center;
        line-height: .4rem;
        color: $bgColor;
    }
}
</style>
