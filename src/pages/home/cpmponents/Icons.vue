<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" />
          </div>
          <p class="icon-describe">{{item.describe}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [
        {
          id: '01',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          describe: '热门景点1'
        },
        {
          id: '02',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          describe: '热门景点2'
        },
        {
          id: '03',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          describe: '热门景点3'
        },
        {
          id: '04',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          describe: '热门景点4'
        },
        {
          id: '05',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          describe: '热门景点5'
        },
        {
          id: '06',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          describe: '热门景点6'
        },
        {
          id: '07',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          describe: '热门景点7'
        },
        {
          id: '08',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          describe: '热门景点8'
        },
        {
          id: '09',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          describe: '热门景点9'
        }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
.icons >>> .swiper-container
  height: 0
  padding-bottom: 50%
.icon
  position: relative
  float: left
  width: 25%
  height: 0
  padding-bottom: 25%
  .icon-img
    position: absolute
    top: 0
    left: 0
    right: 0
    bottom: 0.44rem
    box-sizing: border-box
    padding: 0.1rem
    .icon-img-content
      height: 100%
      display: block
      margin: 0 auto
  .icon-describe
    position: absolute
    left: 0
    right: 0
    bottom: 0
    line-height: 0.44rem
    height: 0.44rem
    text-align: center
    color: $darkTextColor
    ellipsis()
</style>
