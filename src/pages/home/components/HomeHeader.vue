<template>
  <div class="header">
    <div class="header-left"><span class="iconfont">&#xe646;</span></div>
    <input class="header-input" type="text" placeholder="输入城市景点/游玩主题"/>
    <div class="header-city">城市<span class="iconfont">&#xe64a;</span></div>
  </div>
</template>
<script>
export default {
  name: 'HomeHeader'
}
</script>
<style lang='stylus' scoped>
  @import '~styles/variable.styl'
  .header
    display: flex
    height: .86rem
    background-color: $bgColor
    .header-left
      width: .64rem
      line-height: .86rem
      text-align: center
      color: #fff
    .header-input
      flex: 1
      height: .64rem
      line-height:.86rem
      line-height: .64rem
      margin-left: 10px
      margin-top: .11rem
      border-radius: .1rem
      background-color: #fff
      color: #ccc
    .header-city
      width: 1.24rem
      line-height: .86rem
      text-align:center
      color: #fff
</style>
