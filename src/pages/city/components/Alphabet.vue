<template>
  <ul class="list">
    <li class="item"
        v-for="item of letters"
        :ref="item"
        :key="item"
        @click="handleLetterClick"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd">{{item}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      // 数据截流
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    handleLetterClick: function (e) {
      this.$emit('change', e.target.innerText)
    },
    // 触摸事件开始
    handleTouchStart: function () {
      this.touchStatus = true
    },
    // 触摸事件移动
    handleTouchMove: function (e) {
      // 判断触摸事件的状态
      if (this.touchStatus) {
        // 如果计时器存在，则销毁
        if (this.timer) {
          clearTimeout(this.timer)
        }
        // 设置计时器，数据截流
        this.timer = setTimeout(() => {
          // 获取第一个字母的纵向距离
          const touchY = e.touches[0].clientY - 79
          // 获取当前触摸的字母
          const index = Math.floor((touchY - this.startY) / 22)
          // 防止判断范围超出26个字母
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 8)
      }
    },
    // 触摸事件结束
    handleTouchEnd: function () {
      this.touchStatus = false
    }
  }
}
</script>

// 组件样式部分
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.list
  display: flex
  flex-direction: column
  justify-content: center
  position: absolute
  top: 1.58rem
  right: 0
  bottom: 0
  width: 0.4rem
  .item
    line-height: 0.44rem
    text-align: center
    color: $bgColor
</style>
