<template>
  <div class="goods-top">
    <h3>{{topTitle}}</h3>
    <ul>
      <li v-for="item in subs" :class="{active:topSubStatus==item.key}" @mouseenter="topSubStatus=item.key">{{item.name}}</li>
    </ul>
  </div>
</template>
<style>
  .goods-top {
    width: 100%;
    height: 58px;
    line-height: 58px;
  }

  .goods-top h3 {
    float: left;
    font-size:22px;
    font-weight:200;
    color:#333;
  }

  .goods-top ul {
    float: right;
    display: flex;
    flex-flow:row nowrap;
    align-items:center;
    font-size:16px;
    color:#424242;
    margin-top:17px;
  }

  .goods-top ul li {
    width:auto;
    height:24px;
    line-height:24px;
    margin-left:30px;
    cursor: pointer;
    /*border-bottom:2px solid #f5f5f5;*/
  }
  .goods-top ul li.active{
    color:#ff6700;
    border-bottom:2px solid #ff6700;
  }
</style>
<script>
  export default({
    props: ['topTitle', 'subs'],
    data(){
      return {
        topSubStatus: this.subs[0].key
      }
    }
  })
</script>
