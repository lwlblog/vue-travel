<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
      <span class="iconfont back-icon">&#xe743;</span>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      景点详情
      <router-link to="/">
        <span class="iconfont back-icon">&#xe743;</span>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    // 清空全局事件
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-abs
    position: absolute
    top: .15rem
    left: .15rem
    width: .6rem
    height: .6rem
    line-height: .6rem
    border-radius: 50%
    background-color: rgba(0, 0, 0, .5)
    text-align: center
    .iconfont
      color: #fff
      font-size: .5rem
  .header-fixed
    position: fixed
    top: 0
    left: 0
    width: 100%
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
