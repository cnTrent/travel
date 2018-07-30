<template>
    <div class="recommend">
        <div class="recommend-title">
            周末去哪儿
        </div>
        <ul class="bgcolor">
            <li class="item border-bottom" v-for='item in list' :key="item.id">
                <div class="item-img-wrapper">
                     <img :src='item.imgUrl' class="item-img"/>
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
  name: "homeWeekend",
  props:{
    list:Array
  },
  data() {
    return {
    };
  }
};
</script>
<style lang="scss" scoped>
@import "../../../assets/styles/mixins.scss";
.bgcolor{
    background: #f5f5f5
}
.recommend-title {
  line-height: 0.8rem;
  background-color: #eee;
  text-indent: 0.2rem;
}
.item {
    padding-bottom: 0.1rem;
.item-img-wrapper{
    overflow: hidden;
    height: 0;
    padding-bottom: 33.9%;
    .item-img {
    width: 100%;
  }
}
  .item-info {
    background:#fff;
    padding: 0.1rem;
    .item-title {
      line-height: 0.54rem;
      font-size: 0.32rem;
      @include ellipsis;
    }
    .item-desc {
      line-height: 0.4rem;
      color: #ccc;
      @include ellipsis;
    }
  }
}
</style>
