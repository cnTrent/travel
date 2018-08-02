<template>
    <div class="list" ref='wrapper'>
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">
                            {{this.$store.state.city}}
                        </div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div class="button-wrapper"
                         v-for="item in hot" 
                         :key="item.id"
                         @click="handleCityClick(item.name)"
                    >
                        <div class="button">
                            {{item.name}}
                        </div>
                    </div>
                </div>
            </div>
            <div 
                class="area"
                v-for="(item,key) in cityes" 
                :key='key'
                :ref='key'
            >
                <div class="title border-topbottom">{{key}} </div>
                <div class="item-list">
                    <div class="item border-bottom"
                        v-for="innerItem in item" 
                        :key='innerItem.id'
                         @click="handleCityClick(innerItem.name)"
                    >
                        {{innerItem.name}}
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
    props:{
        hot:Array,
        cityes:Object,
        letter:String,
    },
  name: "CityList",
  methods:{
      handleCityClick(city){
          this.$store.dispatch('changeCity',city)
            //路由做页面的跳转
          this.$router.push('/')
      }
  },
  //页面挂载DOM即‘el’之后执行,ref帮助获取DOM，接收是this.$refs.wrapper
  mounted(){
      this.scroll = new BScroll(this.$refs.wrapper)
  },
  //监听器
  watch:{
      letter(){
          if(this.letter){
              const element = this.$refs[this.letter][0]
              console.log(element)
              this.scroll.scrollToElement(element)
          }
          console.log(this.letter)
      }
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
