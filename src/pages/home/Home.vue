<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recommend></home-recommend>
    <home-weekend></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './cpmponents/Header'
import HomeSwiper from './cpmponents/Swiper'
import HomeIcons from './cpmponents/Icons'
import HomeRecommend from './cpmponents/Recommend'
import HomeWeekend from './cpmponents/Weekend'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  }
}
</script>

<style>
</style>
