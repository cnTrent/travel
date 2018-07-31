<template>
    <div class="list" ref='wrapper'>
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">
                            北京
                        </div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">
                            北京
                        </div>
                    </div>
                    <div class="button-wrapper">
                        <div class="button">
                            北京
                        </div>
                    </div>
                    <div class="button-wrapper">
                        <div class="button">
                            北京
                        </div>
                    </div>
                    <div class="button-wrapper">
                        <div class="button">
                            北京
                        </div>
                    </div>
                    <div class="button-wrapper">
                        <div class="button">
                            北京
                        </div>
                    </div>
                    <div class="button-wrapper">
                        <div class="button">
                            北京
                        </div>
                    </div>
                    <div class="button-wrapper">
                        <div class="button">
                            北京
                        </div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">A </div>
                <div class="item-list">
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">A </div>
                <div class="item-list">
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">A </div>
                <div class="item-list">
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                    <div class="item border-bottom">
                        阿尔卑斯
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import BScroll from 'better-scroll'
// const wrapper = document.querySelector('.wrapper')
// const scroll = new BScroll(wrapper)
export default {
  name: "CityList",
  //页面挂载DOM即‘el’之后执行,ref帮助获取DOM，接收是this.$refs.wrapper
  mounted(){
      this.scroll = new BScroll(this.$refs.wrapper)
  }
};
</script>
<style lang="scss" scoped>
@import "../../../assets/styles/varibles.scss";
.border-topbottom {
  &::before {
    border-color: #ccc;
  }
  &::after {
    border-color: #ccc;
  }
}
.list {
    overflow: hidden;
    position: absolute;
    top: 1.58rem;
    left: 0;
    right: 0;
    bottom: 0;
  .title {
    line-height: 0.7rem;
    background-color: #eee;
    padding-left: 0.2rem;
    color: #666;
    font-size: 0.26rem;
  }
  .button-list {
    overflow: hidden;
    padding: 0.1rem;
    padding: 0.1rem 0.6rem 0.1rem 0.1rem;
    .button-wrapper {
      float: left;
      width: 33.33%;
      .button {
        padding: 0.1rem 0;
        border-radius: 0.06rem;
        text-align: center;
        border: 0.02rem solid #ccc;
        margin: 0.1rem;
      }
    }
  }
  .item-list {
    .item {
      line-height: 0.54rem;
      color: #666;
      padding: 0.2rem;
    }
  }
}
</style>
