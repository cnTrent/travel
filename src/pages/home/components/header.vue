<template>
    <div class="header">
       <div class="header-left">
           <span class="iconfont back-icon">&#xe624;</span>
       </div>
       <div class="header-input">
            <span class="iconfont">&#xe632;</span>
            输入城市/景点/游玩主题
        </div>
        <router-link to='/city'>
            <div class="header-right">
           北京
           <span class="iconfont arrow-icon">&#xe64a;</span>
        </div>
        </router-link>
    </div>
</template>

<script>
export default {
  name: "homeHeader",
  data() {
    return {
    };
  }
};
</script>

<style lang="scss" scoped>
@import "../../../assets/styles/varibles.scss";

.header {
  display: flex;
  line-height: 0.86rem;
  background-color: $bgColor;
  color: #fff;
  .header-left {
    width: 0.64rem;
    float: left;
    .back-icon {
      display: block;
      text-align: center;
      font-size: 0.4rem;
    }
  }
  .header-input {
    flex: 1;
    margin-top: 0.12rem;
    height: 0.64rem;
    margin-left: 0.2rem;
    padding-left: 0.2rem;
    background: #fff;
    border-radius: 0.1rem;
    color: #ccc;
    line-height: 0.64rem;
  }
  .header-right {
    width: 1.24rem;
    float: right;
    text-align: center;
    color: #fff;
    .arrow-icon {
      font-size: 0.24rem;
    }
  }
}
</style>

