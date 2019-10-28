<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe658;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe63c;</span>
      输入城市、景点、游玩主题
    </div>
    <router-link to="/city">
    <div class="header-right">
      {{this.city}}
      <span class="iconfont">&#xe659;</span>
    </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  display: flex
  line-height: $headerHeight
  background: $bgColor
  color: #fff
  .header-left
    width: 0.64rem
    float: left
    text-align: center
    .back-icon
      text-align: center
      font-size: 0.4rem
  .header-input
    flex: 1
    margin-top: 0.12rem
    margin-left: 0.2rem
    padding-left: 0.2rem
    line-height: 0.64rem
    height: 0.64rem
    background: #fff
    border-radius: 0.1rem
    color: #ccc
  .header-right
    width: 1.24rem
    float: right
    text-align: center
    color #fff
</style>
