<template>
    <div class="goods-container">
      <goods-top-box></goods-top-box>
      <goods-collocation></goods-collocation>
    </div>
</template>
<style>
  .goods-container{
    width:100%;
    height:5000px;
    background:#f5f5f5;
    padding-bottom:40px;
  }
</style>
<script>
  import GoodsTopBox from './GoodsTopBox'
  import GoodsCollocation from './GoodsCollocation'
    export default({
        data(){
            return {}
        },
      components:{
        GoodsTopBox,GoodsCollocation
      }
    })
</script>
