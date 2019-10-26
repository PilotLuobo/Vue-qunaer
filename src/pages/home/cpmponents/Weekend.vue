<template>
  <div>
    <div class="recommend-title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-describe">{{item.describe}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [
        {
          id: '01',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/40/a78854d5fae37c.jpg_r_640x214_c14de05e.jpg',
          title: '台州必游TOP1',
          describe: '台州地阔海冥冥,云水长和岛屿青'
        },
        {
          id: '02',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/37/c1dfc721e6a7fa.jpg_r_640x214_c43f0f37.jpg',
          title: '夏好倾听',
          describe: '活热夏天,我们一起去漂流戏水吧'
        },
        {
          id: '03',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1507/5c/1ca9ab385cc357.jpg_r_640x214_e881bb46.jpg',
          title: '玩转台州',
          describe: '在台州,周末最好玩'
        },
        {
          id: '04',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1606/18/fccb1a2f45f742.jpg_r_640x214_55564c3f.jpg',
          title: '绍兴必游TOP2',
          describe: '文物之邦,鱼米之乡'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.recommend-title
  margin-top: 0.2rem
  line-height: 0.8rem
  background: #eee
  text-indent: 0.2rem
.item-img-wrapper
  overflow: hidden
  height: 0
  padding-bottom: 33.9%
  .item-img
    width: 100%
.item-info
  min-width: 0
  .item-title
    line-height: 0.54rem
    font-size: 0.32rem
    ellipsis()
  .item-describe
    line-height: 0.4rem
    color: #ccc
    ellipsis()
</style>
