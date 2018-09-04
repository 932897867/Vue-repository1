<template>
  <div>
    <a href="http://localhost:8080/#/list">前往List</a>
    <router-link to="/list">to list</router-link>
    <span class="iconfont">&#xe650;</span>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
  </div>
</template>

<script>
import HomeSwiper from './components/Swiper'
import HomeHeader from './components/Header'
import HomeIcons from './components/Icons'
export default {
  name: 'Home',
  components: {
    HomeSwiper,
    HomeHeader,
    HomeIcons
  }
}
</script>

<style lang="stylus" scoped>
  template {
    color: green;
  }
</style>
