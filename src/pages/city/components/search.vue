<template>
    <div class="search">
       <input class='search-input' type="text" placeholder="输入城市名或拼音"/>
    </div>
</template>
<script>
export default {
    name:"CitySearch"
}
</script>
<style lang="scss" scoped>
@import "../../../assets/styles/varibles.scss";
.search{
    height: .72rem;
    background: $bgColor;
    padding: 0 .1rem;
    .search-input{
        height: .62rem;
        width: 100%;
        box-sizing: border-box;
        padding: 0 .1rem;
        text-align: center;
        line-height: .62rem;
        border-radius: .06rem;
        color: #666;
    }
}
</style>
