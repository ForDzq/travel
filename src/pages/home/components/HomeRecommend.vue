<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <img :src="item.imgUrl" alt="图片">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-detail">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  },
  data () {
    return {
      recommendList: [{
        id: '001'
      }]
    }
  }
}
</script>
<style lang='stylus' scoped>
  .recommend-title
    height: .6rem
    line-height: .6rem
    background: #eee
    padding-left: .2rem
    margin-top: .2rem
  .item
    display: flex
    align-content: middle
    height: 1.8rem
    img
     width: 1.6rem
     height: 1.6rem
     padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      line-height: .4rem
      .item-title
        color: #999
      .item-desc
        font-size: .27rem
        color: #ccc
      .item-detail
        background: yellow
        padding: .05rem .08rem
        border-radius: .1rem
        margin-top: .1rem
</style>
