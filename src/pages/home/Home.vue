<template>
  <div>
    <home-header :city='city'></home-header>
    <home-swiper :list='swiperList'></home-swiper>
    <home-icon :list='iconList' ></home-icon>
    <home-recommend :list='recommendList'></home-recommend>
    <home-weekend :list='weekendList'></home-weekend>
  </div>
</template>
<script>
import HomeHeader from 'pages/home/components/HomeHeader'
import HomeSwiper from 'pages/home/components/HomeSwiper'
import HomeIcon from 'pages/home/components/HomeIcon'
import HomeRecommend from 'pages/home/components/HomeRecommend'
import HomeWeekend from 'pages/home/components/HomeWeekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcon,
    HomeRecommend,
    HomeWeekend,
  },
  data () {
   return {
     city: '',
     swiperList: [],
     iconList: [],
     recommendList: [],
     weekendList: []
   }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      console.log(res)
        res = res.data
        if(res.ret && res.data){
          const data = res.data
          this.city = data.city
          this.swiperList = data.swiperList
          this.iconList = data.iconList
          this.recommendList = data.recommendList
          this.weekendList =data.weekendList
        }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>
<style lang='stylus' scoped>
</style>
