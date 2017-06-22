<template>
  <div class="header-wrap">
    <h3 class="title">{{title}}</h3>
    <a :Lhref="moreUrl" v-show="isShowMore"><span>查看全部<i class="fa fa-chevron-circle-right fa-fw"></i></span></a>
  </div>
</template>
<style >
  /*  .header-wrap {
      position: relative;
    }

    .title {
      margin: 0;
      font-size: 22px;
      font-weight: 200;
      line-height: 58px;
      color: #333;
    }*/
  .header-wrap {
    width: 1226px;
    height: 58px;
    line-height: 58px;
    position: relative;
    /*border:1px solid red;*/
  }

  .header-wrap h3 {
    float: left;
    margin: 0;
    font-size: 22px;
    font-weight: 200;
    line-height: 58px;
    color: #333;
  }

  .header-wrap span {
    float: right;
    color: #424242;
    font-size: 16px;
    display: block;
    cursor: pointer;
  }

  .header-wrap span i {
    color: #b0b0b0;
    font-size: 20px;
  }

  .header-wrap span:hover {
    color: #ff6700;
  }

  .header-wrap span:hover i {
    color: #ff6700;
  }
</style>
<script>
  export default({
    props: ['title', 'isShowMore', 'moreUrl'],
    data(){
      return {}
    }
  })
</script>
