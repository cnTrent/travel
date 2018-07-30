<template>
    <div class="recommend">
        <div class="recommend-title">
            周末去哪儿
        </div>
        <ul class="bgcolor">
            <li class="item border-bottom" v-for='item in recommentList' :key="item.id">
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
  data() {
    return {
      recommentList: [
        {
          id: "0001",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1505/53/02091f1ee43d0a.jpg_r_640x214_2e3256b1.jpg",
          title: "北京清凉避暑胜地",
          desc: "到大自然中享受“天然空调”的清凉"
        },
        {
          id: "0002",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1505/53/02091f1ee43d0a.jpg_r_640x214_2e3256b1.jpg",
          title: "北京清凉避暑胜地",
          desc: "到大自然中享受“天然空调”的清凉"
        },
        {
          id: "0003",
          imgUrl:
            "http://img1.qunarzz.com/sight/source/1505/53/02091f1ee43d0a.jpg_r_640x214_2e3256b1.jpg",
          title: "北京清凉避暑胜地",
          desc: "到大自然中享受“天然空调”的清凉"
        }
      ]
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
  margin-top: 0.2rem;
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
