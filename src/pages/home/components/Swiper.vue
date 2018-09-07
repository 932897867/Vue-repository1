<template>
  <div class="wraper">
    <swiper :options="swiperOption" v-if="list.length">
      <swiper-slide v-for="item of list" :key="item.id"><img class="swiper-img" :src="item.imgUrl"></swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
        // paginationType: 'fraction'
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wraper >>> .swiper-pagination-bullet-active
    background: red
  .wraper
    width: 100%
    height: 0
    padding-bottom: 31.25%
    overflow: hidden
    .swiper-img
      width: 100%
    .swiper-pagination
      position: absolute
      top: 25vw
</style>
