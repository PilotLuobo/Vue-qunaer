<template>
  <div>
    <div class="weekend-title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of weekendList" :key="item.id">
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
  props: {
    weekendList: Array
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.weekend-title
  line-height: 0.8rem
  background: #eee
  text-indent: 0.2rem
.item-img-wrapper
  overflow: hidden
  height: 0
  padding-bottom: 37.09%
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
