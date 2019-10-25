<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recommend></home-recommend>
  </div>
</template>

<script>
import HomeHeader from './cpmponents/Header'
import HomeSwiper from './cpmponents/Swiper'
import HomeIcons from './cpmponents/Icons'
import HomeRecommend from './cpmponents/Recommend'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend
  }
}
</script>

<style>
</style>
