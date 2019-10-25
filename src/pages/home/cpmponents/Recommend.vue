<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item">
        <div class="item-imgwrapper">
          <img class="item-img" src />
        </div>
        <div class="item-info">
          <p class="item-title"></p>
          <p class="item-describe"></p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend'
}
</script>

<style lang="stylus" scoped>
.recommend-title
  margin-top: 0.2rem
  line-height: 0.8rem
  background: #eee
  text-indent: 0.2rem
.item
  overflow: hidden
  display: flex
  height: 1.9rem
  background: red
</style>
