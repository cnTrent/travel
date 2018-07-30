<template>
    <div class="icons">
        <swiper>
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
  data(){
      return{
          iconList:[
              {
                  id:"0001",
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                  desc:'景点门票'
              },
               {
                  id:"0002",
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
                  desc:'北京必游'
              },
              {
                  id:"0003",
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
                  desc:'夏日玩水'
              },
               {
                  id:"0004",
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
                  desc:'北京必游'
              },
               {
                  id:"0005",
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
                  desc:'北京必游'
              },
               {
                  id:"0006",
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
                  desc:'北京必游'
              },
               {
                  id:"0007",
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/95/8d02011d149bdb02.png',
                  desc:'北京必游'
              },
               {
                  id:"0008",
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
                  desc:'游乐场'
              },
               {
                  id:"0009",
                  imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
                  desc:'全部玩乐'
              },
          ]
      }
  },
  computed:{
      pages(){
          //把其分割成两个数组
          const pages = []
          this.iconList.forEach((item,index)=>{
              const page = Math.floor(index/8)
              if(!pages[page]){
                  pages[page] = []
              }
              pages[page].push(item)
          })
        return pages
      }
  }
};
</script>
<style lang="scss" scoped>
@import "../../../assets/styles/varibles.scss";
@import "../../../assets/styles/mixins.scss";

.icons>>>.swiper-container{
    height: 0;
    padding-bottom: 50%;
}
.icons {
    margin-top: .2rem;
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
      @include  ellipsis 
    }
  }
}
</style>
