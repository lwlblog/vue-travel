<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont back-icon">&#xe743;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe7b3;</span>
      输入城市/景点/游玩主题
    </div>
    <div class="header-right">
      {{this.city}}
      <span class="iconfont arrow-icon">&#xe6aa;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display: flex
    height: .86rem
    display: flex
    align-items: center
    background-color: $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
      text-align: center
      .back-icon
        font-size: .6rem
    .header-input
      flex: 1
      height: .64rem
      line-height: .64rem
      margin: 0 .1rem
      padding-left: .2rem
      background-color: #fff
      border-radius: .1rem
      color: #ccc
    .header-right
      width: 1.24rem
      float: right
      text-align: center
      .arrow-icon
        margin-left: -.06rem
</style>
