<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1901/46/46416618f4ae8e95a3.img.png_r_800x800_f01d985b.png">
      <div class="banner-info">
        <div class="banner-title">大连圣亚海洋公园（AAAA景区）</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe889;</span>39</div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      imgs: [
        'http://img1.qunarzz.com/sight/p0/1901/46/46416618f4ae8e95a3.img.png_r_800x800_f01d985b.png',
        'http://img1.qunarzz.com/sight/p0/1508/a5/4003f9dd7bebf61eccbf64046e26d487.water.jpg_r_800x800_4701d58f.jpg',
        'http://img1.qunarzz.com/sight/p0/1507/b9/7ce37fa2e77ad7b9cb49d54352c8e357.water.jpg_r_800x800_c52ed9f4.jpg'
      ],
      showGallary: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>

<style lang="stylus" scoped>
.banner
  position relative
  overflow hidden
  height: 0
  padding-bottom 55%
  .banner-img
    width 100%
  .banner-info
    display flex
    position absolute
    left 0
    right 0
    bottom 0
    line-height 0.6rem
    color #ffffff
    background-image linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
    .banner-title
      flex 1
      font-size 0.32rem
      padding 0 0.2rem
    .banner-number
      margin-top 0.14rem
      padding 0 0.4rem
      line-height 0.32rem
      height 0.32rem
      border-radius 0.2rem
      background rgba(0,0,0,0.8)
      font-size 0.24rem
      .banner-icon
        font-size 0.24rem
</style>
