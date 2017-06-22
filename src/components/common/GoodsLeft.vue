<template>
  <ul class="goods-left">
    <li v-for="item in leftGoods">
      <a :href="item.sourceUrl" target="_blank">
        <img :src="item.imgUrl" alt="">
      </a>
    </li>
  </ul>
</template>
<style>
  .goods-left{
    float: left;
    width:234px;
    height:auto;

  }
  .goods-left li{
    width:234px;
    height:300px;
    margin:14px 0;
  }
  .goods-left li:hover{
    transform:translateY(-2px);
    box-shadow:5px 5px 20px #ccc;
  }
  .goods-left li img{
    width:234px;
    height:300px;
  }
</style>
<script>

  export default({
    props: ['leftGoods'],
    data(){
      return {}
    }
  })
</script>
