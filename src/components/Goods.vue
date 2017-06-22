<template>
    <div class="goods-container">
      <goods-top-box></goods-top-box>
      <goods-collocation></goods-collocation>
      <goods-accessories></goods-accessories>
      <goods-around></goods-around>
      <recommend></recommend>
      <hot-product></hot-product>
      <goods-content v-on:play="play"></goods-content>
      <m-video  ></m-video>
    </div>
</template>
<style>
  .goods-container{
    width:100%;
    height:auto;
    background:#f5f5f5;
    padding-bottom:340px;
  }
</style>
<script>
  import GoodsTopBox from './GoodsTopBox'
  import GoodsCollocation from './GoodsCollocation'
  import GoodsAccessories from './GoodsAccessories'
  import GoodsAround from './GoodsAround'
  import Recommend from './Recommend'
  import HotProduct from './HotProduct'
  import GoodsContent from './GoodsContent'
  import mVideo from './Video'
    export default({
        data(){
            return {}
        },
      created:function () {
        this.$on('play',function (opts) {
          console.log('evtPlayVideo')
        })
      },
      methods:{
        play:function () {
          console.log(1);
        }
      },
      components:{
        GoodsTopBox,GoodsCollocation,GoodsAccessories,GoodsAround,Recommend,
        HotProduct,GoodsContent,mVideo
      }
    })
</script>
