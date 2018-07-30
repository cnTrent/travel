<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <swiper-slide v-for="item in swiperList" :key="item.id">
                <img :src="item.imgUrl" class="swiper-img"/>
            </swiper-slide>
          <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>
<script>
export default {
  name: "HomeSwiper",
  data() {
    return {
      swiperOption: {
        pagination: {
          el: ".swiper-pagination"
        },
        loop:true
      },
      swiperList: [
        {
          id: "0001",
          imgUrl:
            "https://source.qunarzz.com/site/images/wap/home/recommend/iphoneplus/anquan_20180716.png"
        },
        {
          id: "0002",
          imgUrl:
            "https://source.qunarzz.com/site/images/wap/home/recommend/iphoneplus/sc_sqdc_20180727.jpg"
        }
      ]
    };
  }
};
</script>
<style lang="scss" scoped>
.wrapper {
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom: 31.25%;
  .swiper-img {
    width: 100%;
  }
}
</style>
