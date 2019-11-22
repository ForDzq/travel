<template>
  <div>
    <div class="icon">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(page,index) of pages" :key="index">
          <div class="icon-box" v-for="item of page" :key="item.id">
            <div class='img-box'>
              <img :src="item.imgUrl" alt="图片">
            </div>
            <div class="icon-box-desc">{{item.desc}}</div>
          </div>
        </swiper-slide>
      </swiper>
    </div>
    <div class="swiper-pagination"  slot="pagination"></div>
  </div>
</template>
<script>
export default {
  name: 'HomeIcon',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        loop: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
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
  @import '~styles/mixins.styl'
  .icon >>> .swiper-container
    height: 0
    width: 100%
    padding-bottom: 50%
    overflow: hidden
  .icon-box
    position: relative
    float: left
    width: 25%
    height: 0
    padding-bottom: 25%
    .img-box
      overflow: hidden
      position: absolute
      text-align: center
      box-sizing: border-box
      padding: .13rem
      top: 0
      left: 0
      right: 0
      bottom: .4rem
      img
        height: 100%
    .icon-box-desc
      position: absolute
      text-align: center
      bottom: 0
      left: 0
      right: 0
      padding-bottom: .1rem
      ellipsis()
</style>
