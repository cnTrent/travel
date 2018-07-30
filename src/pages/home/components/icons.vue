<template>
    <div class="icons">
        <swiper :options="swiperOption">
            <swiper-slide v-for="(page,index) in pages" :key="index">
                <div class="icon"  v-for="icon in page" :key="icon.id">
                    <div class="icon-img">
                    <img class="icon-img-content" :src="icon.imgUrl"/>
                    </div>
                    <p class="icon-desc">{{icon.desc}}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>
<script>
export default {
  name: "homeIcons",
  props: {
    list: Array
  },
  data() {
    return {
      swiperOption: {
        autoplay:false
      }
    };
  },
  computed: {
    pages() {
      //把其分割成两个数组
      const pages = [];
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8);
        if (!pages[page]) {
          pages[page] = [];
        }
        pages[page].push(item);
      });
      return pages;
    }
  }
};
</script>
<style lang="scss" scoped>
@import "../../../assets/styles/varibles.scss";
@import "../../../assets/styles/mixins.scss";

.icons >>> .swiper-container {
  height: 0;
  padding-bottom: 50%;
}
.icons {
  margin-top: 0.2rem;
  .icon {
    position: relative;
    overflow: hidden;
    float: left;
    height: 0;
    width: 25%;
    padding-bottom: 25%;
    .icon-img {
      position: absolute;
      left: 0;
      top: 0;
      right: 0;
      bottom: 0.44rem;
      box-sizing: border-box;
      padding: 0.1rem;
      .icon-img-content {
        display: block;
        margin: 0 auto;
        height: 100%;
      }
    }
    .icon-desc {
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      height: 0.44rem;
      line-height: 0.44rem;
      color: $darkTextColor;
      text-align: center;
      @include ellipsis;
    }
  }
}
</style>
