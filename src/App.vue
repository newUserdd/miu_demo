<template>
  <div id="app">
    <top-bar></top-bar>
    <top-header></top-header>
    <top-banner></top-banner>
    <top-sub></top-sub>
    <goods></goods>
    <temp-footer></temp-footer>
  </div>
</template>

<script>
//  require('./assets/css/base.css')
  import TopBar from './components/TopBar'
  import TopHeader from './components/TopHeader'
  import TopBanner from './components/TopBanner'
  import TopSub from './components/TopSub'
  import Goods from './components/Goods'
  import TempFooter from './components/TempFooter'

  export default {
    name: 'app',
    components: {
      topBar: TopBar,
      topHeader: TopHeader,
      TopBanner: TopBanner,
      TopSub: TopSub,
      Goods: Goods,
      TempFooter
    },
    created:function () {
      this.$on('play',function (opts) {
          console.log(opts,'opts');
      })
    },
    methods:{

    }
  }
</script>

<style>
  @import "./assets/css/base.css";
</style>
