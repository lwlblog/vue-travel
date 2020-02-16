<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <span class="iconfont back-icon">&#xe743;</span>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position: relative
    overflow: hidden
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #fff
    font-size: .32rem
    background-color: $bgColor
    .back-icon
      position: absolute
      font-size: .6rem
      top: 0
      left: 0
      bottom: 0
      color: #fff
</style>
