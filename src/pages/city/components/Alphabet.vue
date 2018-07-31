<template>
    <ul class="list">
        <li 
            class="item" 
            v-for="item in lettres" 
            :key='item'
            :ref="item"
            @click='handleLetterClick'
            @touchstart='handleTouchcStart'
            @touchmove='handleTouchMouv'
            @touchend='handleTouchend'
        >
            {{item}}
        </li>
    </ul>
</template>
<script>
export default {
  name: "CityAlphabet",
  props: {
    cityes: Object
  },
  data() {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    };
  },
  //updated页面数据被更新时，同时页面完成自己的渲染之后，updated就会立即执行
  updated() {
    this.startY = this.$refs["A"][0].offsetTop;
  },
  computed: {
    lettres() {
      const lettres = [];
      for (let i in this.cityes) {
        lettres.push(i);
      }
      return lettres;
    }
  },
  methods: {
    handleLetterClick(e) {
      //$emit()向外触发事件
      this.$emit("change", e.target.innerText);
      // console.log(e.target.innerText)
    },
    handleTouchcStart() {
      this.touchStatus = true;
    },
    handleTouchMouv(e) {
      if (this.touchStatus) {
        // const startY = this.$refs["A"][0].offsetTop;
        //函数节流
        if (this.timer) {
          clearTimeout(this.timer);
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 79;
          const index = Math.floor((touchY - this.startY) / 20);
          if (index >= 0 && index < this.lettres.length) {
            this.$emit("change", this.lettres[index]);
          }
          console.log(index);
        }, 16);
      }
    },
    handleTouchend() {
      this.touchStatus = false;
    }
  }
};
</script>
<style lang="scss" scoped>
@import "../../../assets/styles/varibles.scss";
.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  top: 1.58rem;
  right: 0;
  bottom: 0;
  width: 0.4rem;
  .item {
    text-align: center;
    line-height: 0.4rem;
    color: $bgColor;
  }
}
</style>
