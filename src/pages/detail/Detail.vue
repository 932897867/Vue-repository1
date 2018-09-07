<template>
  <div>
    <banner
      :bannerImg="bannerImg"
      :gallaryImgs="gallaryImgs"
      :sightName="sightName"></banner>
  </div>
</template>

<script>
import Banner from './components/Banner'
import axios from 'axios'
export default {
  name: 'Detail',
  data () {
    return {
      bannerImg: '',
      categoryList: [],
      gallaryImgs: [],
      sightName: ''
    }
  },
  components: {
    Banner
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json')
        .then(this.getDetailInfoSucc)
    },
    getDetailInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.bannerImg = data.bannerImg
        this.categoryList = data.categoryList
        this.gallaryImgs = data.gallaryImgs
        this.sightName = data.sightName
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
