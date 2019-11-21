<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icon></home-icon>
  </div>
</template>
<script>
import HomeHeader from 'pages/home/components/HomeHeader'
import HomeSwiper from 'pages/home/components/HomeSwiper'
import HomeIcon from 'pages/home/components/HomeIcon'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcon
  }
}
</script>
<style lang='stylus' scoped>

</style>
