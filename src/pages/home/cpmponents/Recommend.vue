<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-describe">{{item.describe}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [
        {
          id: '01',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
          title: '上海迪士尼乐园',
          describe: '迪士尼乐园,情人旅行必选之地'
        },
        {
          id: '02',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201405/13/cc6b2870049aa5086badad72fed0d36d.jpg_200x200_85a759dc.jpg',
          title: '天台山琼台仙谷',
          describe: '天台山琼台仙谷,节假日旅行必选之地'
        },
        {
          id: '03',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1606/65/6520ca836ebee29b90.img.jpg_200x200_6a78b9f5.jpg',
          title: '天台龙穿峡漂流',
          describe: '天台龙穿峡漂流,节假日旅行必选之地'
        },
        {
          id: '04',
          imgUrl: 'http://img1.qunarzz.com/sight/p74/201211/05/dba2176afa7fcf8a93835fbb.jpg_200x200_d4a635eb.jpg',
          title: '台州海洋世界',
          describe: '台州海洋世界,节假日旅行必选之地'
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
.item
  overflow: hidden
  display: flex
  height: 1.9rem
  // background: red
  .item-img
    width: 1.7rem
    height: 1.7rem
    padding: 0.1rem
  .item-info
    padding 0.1rem
    .item-title
      line-height: 0.54rem
      font-size: 0.32rem
      ellipsis()
    .item-describe
      line-height: 0.4rem
      color: #ccc
      ellipsis()
    .item-button
      line-height: 0.44rem
      background: #ff9300
      padding: 0 0.2rem
      border-radius: 0.06rem
      margin-top: 0.16rem
</style>
