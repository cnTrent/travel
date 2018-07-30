<template>
    <div class="recommend">
        <div class="recommend-title">
            热销推荐
        </div>
        <ul>
            <li class="item border-bottom" v-for='item in recommentList' :key="item.id">
                    <img :src='item.imgUrl' class="item-img"/>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
  name: "homeRecommend",
  data() {
    return {
      recommentList: [
        {
          id: "0001",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1602/67/67feeab24cfc82bb90.water.jpg_200x200_af2a01b1.jpg",
          title: "太平洋海底世界",
          desc: "海底隧道是太平洋海底世界的主体部分"
        },
        {
          id: "0002",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1602/67/67feeab24cfc82bb90.water.jpg_200x200_af2a01b1.jpg",
          title: "太平洋海底世界",
          desc: "海底隧道是太平洋海底世界的主体部分"
        },
        {
          id: "0003",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1602/67/67feeab24cfc82bb90.water.jpg_200x200_af2a01b1.jpg",
          title: "太平洋海底世界",
          desc: "海底隧道是太平洋海底世界的主体部分"
        },
      ]
    };
  }
};
</script>
<style lang="scss" scoped>
@import "../../../assets/styles/mixins.scss";
.recommend-title {
  line-height: 0.8rem;
  background-color: #eee;
  text-indent: 0.2rem;
  margin-top: 0.2rem;
}
.item {
  overflow: hidden;
  display: flex;
  height: 1.9rem;
  .item-img {
    width: 1.7rem;
    height: 1.7rem;
    padding: 0.1rem;
  }
  .item-info {
    flex: 1;
    padding: 0.1rem;
    min-width: 0;
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
    .item-button {
      line-height: 0.44rem;
      margin-top: 0.16rem;
      background-color: #ff9300;
      padding: 0 0.2rem;
      border-radius: 0.06rem;
      color: #fff;
    }
  }
}
</style>
