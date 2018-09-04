<template>
  <div>
    <a href="http://localhost:8080/#/list">前往List</a>
    <router-link to="/list">to list</router-link>
    <span class="iconfont">&#xe650;</span>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recommend></home-recommend>
  </div>
</template>

<script>
import HomeSwiper from './components/Swiper'
import HomeHeader from './components/Header'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
export default {
  name: 'Home',
  components: {
    HomeSwiper,
    HomeHeader,
    HomeIcons,
    HomeRecommend
  }
}
</script>

<style lang="stylus" scoped>
  template {
    color: green;
  }
</style>
