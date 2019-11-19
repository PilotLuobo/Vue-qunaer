<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
      <div class="iconfont header-abs-back">&#xe658;</div>
    </router-link>
    <div class="header-fixed" :style="opacityStyle" v-show="!showAbs">
      <router-link to="/">
        <div class="iconfont header-fixed-back">&#xe658;</div>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      // console.log(document.documentElement.scrollTop)
      if (top > 60) {
        // 渐隐渐显效果
        let opacity = top / 140
        // 判断opacity的值是否超过1，若超过则为1，不超过则为计算的opacity值
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header-abs
  position absolute
  left: 0.2rem
  top 0.2rem
  width 0.8rem
  height 0.8rem
  border-radius: 0.4rem
  text-align center
  line-height 0.8rem
  background rgba(0,0,0,0.8)
  .header-abs-back
    color #fff
    font-size 0.4rem
.header-fixed
  border-radius 1px
  z-index 2
  position: fixed
  height: $headerHeight
  line-height: $headerHeight
  // overflow: hidden
  text-align: center
  color: #fff
  background: $bgColor
  font-size: 0.32rem
  top 0
  left 0
  right 0
  .header-fixed-back
    width: 0.64rem
    text-align: center
    font-size: 0.4rem
    position: absolute
    top: 0
    left: 0
    color: #fff
</style>
