<template>
  <div>
    <div class="weekend-title">周末去哪儿</div>
    <ul>
       <li v-for="item of list" :key="item.id">
          <div class="weekend-wrapper">
            <div class="img-wrapper">
              <img :src="item.imgUrl" alt="图片">
            </div>
            <p class="img-title">{{item.title}}</p>
            <p class="img-desc">{{item.desc}}</p>
          </div>
       </li>   
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}
</script>
<style lang="stylus" scoped>
  .weekend-title
    height: .6rem
    line-height: .6rem
    padding-left: .2rem
    background: #ccc
    margin-top: .2rem
  .weekend-wrapper
    height: 4rem
    width: 100%
    .img-wrapper
      height: 0
      width: 100%
      padding-bottom: 36.64%
      overflow: hidden
      img
       width: 100%
    .img-title
      height: .5rem
      line-height: .5rem
      color: #999
      padding-left: .2rem
    .img-desc
      height: .5rem
      line-height: .5rem
      color: #999
      padding-left: .2rem
      margin-bottom: .2rem
</style>
