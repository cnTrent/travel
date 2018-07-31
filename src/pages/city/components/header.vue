<template>
    <div class="header">
       城市选择
       <router-link to='/'>
            <span class="iconfont header-back">&#xe624;</span>
       </router-link>
    </div>
</template>
<script>
export default {
    name:"CityHeader"
}
</script>
<style lang="scss" scoped>
@import "../../../assets/styles/varibles.scss";
.header{
    overflow: hidden;
    height: .86rem;
    line-height: .86rem;
    text-align: center;
    background: $bgColor;
    color: #fff;
    font-size: .32rem;
    position: relative;
    .header-back{
        position: absolute;
        top: 0;
        left: 0;
        display: block;
        width: .64rem;
        text-align: center;
        font-size: .4rem;
        color: #fff
    }
}
</style>
