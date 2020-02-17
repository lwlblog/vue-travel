<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont back-icon">&#xe743;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe7b3;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe6aa;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display: flex
    height: $headerHeight
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
      min-width: 1.04rem
      padding: .1rem
      float: right
      text-align: center
      color: #fff
      .arrow-icon
        margin-left: -.06rem
</style>
