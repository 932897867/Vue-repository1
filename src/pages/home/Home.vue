<template>
  <div>
    <router-link to="/city">{{this.$store.state.city}}</router-link>
    <span class="iconfont">&#xe650;</span>
    <router-link to="/list">to list</router-link>
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
  </div>
</template>

<script>
import HomeSwiper from './components/Swiper'
import HomeHeader from './components/Header'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeSwiper,
    HomeHeader,
    HomeIcons,
    HomeRecommend
  },
  data () {
    return {
      recommendList: [],
      swiperList: [],
      iconList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.recommendList = data.recommendList
        this.swiperList = data.swiperList
        this.iconList = data.iconList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style lang="stylus" scoped>
  template {
    color: green;
  }
</style>
