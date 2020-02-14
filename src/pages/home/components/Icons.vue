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
  data () {
    return {
      swiperOption: {
        autoplay: false
      },
      iconList: [{
        'id': '0001',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        'desc': '景点门票'
      }, {
        'id': '0002',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1711/df/86cbcfc533330d02.png',
        'desc': '滑雪季'
      }, {
        'id': '0003',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1710/a6/83f636bd75ae6302.png',
        'desc': '泡温泉'
      }, {
        'id': '0004',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/35/2640cab202c41b02.png',
        'desc': '动植园'
      }, {
        'id': '0005',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/d0/e09575e66f4aa402.png',
        'desc': '游乐园'
      }, {
        'id': '0006',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/59/569d3c096e542502.png',
        'desc': '必游榜单'
      }, {
        'id': '0007',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/17/4bd370f3eb1acd02.png',
        'desc': '演出'
      }, {
        'id': '0008',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/7f/b1ea3c8c7fb6db02.png',
        'desc': '城市观光'
      }, {
        'id': '0009',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/7f/b1ea3c8c7fb6db02.png',
        'desc': '城市观光'
      }]
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
