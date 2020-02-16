<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon-item" v-for="item of page" :key="item.id">
          <div class="icon">
            <img :src="item.imgUrl" alt="">
            <p>{{item.desc}}</p>
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
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
  @import '~styles/varibles.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icon-item
    position: relative
    float: left
    width: 25%
    height: 0
    overflow: hidden
    padding-bottom: 25%
    .icon
      position: absolute
      width: 100%
      height: 100%
      display: flex
      flex-direction: column
      justify-content: center
      align-items: center
      img
        width: 50%
      p
        width: 80%
        text-align: center
        padding-top: .16rem
        color: $darkTextColor
        ellipsis()
</style>
