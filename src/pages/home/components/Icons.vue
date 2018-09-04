<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png">
          </div>
          <p class="img-desc">景点门票</p>
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
      list: [{
        id: '001',
        item: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        desc: 'asdsdasd'
      }, {
        id: '002',
        item: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        desc: 'asdsdasd'
      }, {
        id: '003',
        item: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        desc: 'asdsdasd'
      }, {
        id: '004',
        item: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        desc: 'asdsdasd'
      }, {
        id: '005',
        item: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        desc: 'asdsdasd'
      }, {
        id: '006',
        item: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        desc: 'asdsdasd'
      }, {
        id: '007',
        item: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        desc: 'asdsdasd'
      }, {
        id: '008',
        item: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        desc: 'asdsdasd'
      }, {
        id: '009',
        item: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        desc: 'asdsdasd'
      }]
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
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons
    width: 100%
    height: 0
    padding-bottom: 50%
    margin-top: .1rem
    overflow: hidden
    .icon
      position: relative
      overflow: hidden
      float: left
      width: 25%
      height: 0
      padding-bottom: 25%
      .icon-img
        position: absolute
        rop: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: .1rem
        .icon-img-content
          display: block
          margin: 0 auto
          width: 75%
          height: 75%
      .img-desc
        position: absolute
        position: absolute
        left: 0
        right: 0
        bottom: 0
        height: .44rem
        line-height: .44rem
        text-align: center
        color: $darkTextColor
</style>
