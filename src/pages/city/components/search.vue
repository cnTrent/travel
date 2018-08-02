<template>
    <div>
        <div class="search">
            <input 
                class='search-input' 
                type="text" 
                placeholder="输入城市名或拼音"
                v-model="keyword"
            />
        </div>
        <div class="search-content" ref='search' v-show="keyword">
            <ul>
                <li class="search-item border-botton"
                     v-for="item in list" 
                     :key='item.id'
                      @click="handleCityClick(item.name)"
                >
                    {{item.name}}
                </li>
                <li class="search-item border-botton" v-show="hasNoData">
                    没有找到匹配的数据
                </li>
            </ul>
        </div>
    </div>
</template>
<script>
import BScroll from 'better-scroll'
export default {
  name: "CitySearch",
  props: {
    cityes:Object,
  },
  data() {
    return {
      keyword: "",
      list: [],
      timer: null
    };
  },
  watch: {
    keyword() {
      if (this.timer) {
        clearTimeout(this.timer);
      }
      this.timer = setTimeout(() => {
        const result = [];
        if(!this.keyword){
            this.list = []
            return
        }
        for (let i in this.cityes) {
          this.cityes[i].forEach(value => {
            if (
              value.spell.indexOf(this.keyword) > -1 ||
              value.name.indexOf(this.keyword)>-1
            ) {
              result.push(value);
            }
          });
        }
        this.list = result
      }, 100);
    }
  },
  mounted(){
      this.scroll = new BScroll(this.$refs.search)
  },
  computed:{
      hasNoData(){
          return !this.list.length
      }
  },
   methods:{
      handleCityClick(city){
          this.$store.dispatch('changeCity',city)
          //路由做页面的跳转
          this.$router.push('/')
      }
  },
};
</script>
<style lang="scss" scoped>
@import "../../../assets/styles/varibles.scss";
.search {
  height: 0.72rem;
  background: $bgColor;
  padding: 0 0.1rem;
  .search-input {
    height: 0.62rem;
    width: 100%;
    box-sizing: border-box;
    padding: 0 0.1rem;
    text-align: center;
    line-height: 0.62rem;
    border-radius: 0.06rem;
    color: #666;
  }
}
.search-content {
  overflow: hidden;
  position: absolute;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;
  background: #f5f5f5;
  z-index: 1;
  .search-item{
      line-height: .62rem;
      color: #666;
      padding-left: .2rem;
      background: #fff;
  }
}
</style>
