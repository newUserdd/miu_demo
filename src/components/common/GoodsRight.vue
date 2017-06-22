<template>
  <div class="goods-right">
    <ul class="goods-right-content">
      <li @mouseenter="item.reviewStatus=true" @mouseleave="item.reviewStatus=false" v-for="(item,index) in currGoods" class="goods-right-item" v-if="index<currGoods.length-1">
        <span class="discount-label" :class="item.discountType">{{item.discount}}</span>
        <a :href="item.sourceUrl" target="_blank">
          <img :src="item.imgUrl" alt="">
          <h3>{{item.title}}</h3>
        </a>
        <p class="goods-price">
          {{item.price}}元
          <span>{{item.oldPrice}}元</span>
        </p>
        <p class="goods-rank">{{item.heat}}人评价</p>
        <transition name="fade2">
          <div v-show="item.reviewStatus" class="review">
            <span class="review-content">{{item.reviewDesc}}</span>
            <span class="review-author">来自于{{item.reviewAuthor}}的评价</span>
          </div>
        </transition>
      </li>
      <ul class="goods-right-small">
        <li class="item-small" v-if="lastGoods">
          <a href="">
            <div>
              <h3>{{lastGoods.title}}</h3>
              <span>{{lastGoods.price}}元</span>
            </div>
            <img :src="lastGoods.imgUrl" alt="">
          </a>
        </li>
        <li class="item-small more">
          <a href="">
            <div>
              <h3>浏览更多</h3>
              <span>热门</span>
            </div>
           <i class="fa fa-arrow-circle-right fa-4x fa-fw icon-arrow"></i>
          </a>
        </li>
      </ul>
    </ul>
  </div>
</template>
<style>
  .goods-right{
    float: left;
    width:992px;
    height:628px;

  }
  .goods-right .goods-right-content{
    display: flex;
    flex-flow:row wrap;
    justify-content:flex-start;
    width:100%;
    height:100%;
    margin-top:15px;

  }
  .goods-right .goods-right-content .goods-right-item{
    position: relative;
    margin:0 0 14px 14px;
    padding:20px 0;
    width:234px;
    height:260px;
    background:#fff;
    cursor: pointer;
  }
  .goods-right .goods-right-content .goods-right-item:hover{
    transform:translateY(-1px);
    box-shadow:5px 5px 20px #ccc;
  }
  /*.goods-right .goods-right-content .goods-right-item:hover .review{
    height: 76px;
    opacity: 1;
  }*/
  .goods-right .goods-right-content .goods-right-item .discount-label{
    position: absolute;
    top:0;
    left:50%;
    width:64px;
    height:20px;
    margin-left:-32px;
    font-size:12px;
    color:#fff;
    text-align:center;
    line-height:20px;
    z-index:4;
  }
  .goods-right .goods-right-content .goods-right-item .discount-label.free{
    background-color: #ffac13;
  }
  .goods-right .goods-right-content .goods-right-item .discount-label.new{
    background-color: #83c44e;
  }
  .goods-right .goods-right-content .goods-right-item .discount-label.discount{
    background-color: #e53935;
  }

  .goods-right .goods-right-content .goods-right-item a{}
  .goods-right .goods-right-content .goods-right-item a img{
    display: block;
    width: 160px;
    height: 160px;
    margin: 0 auto;
  }
  .goods-right .goods-right-content .goods-right-item a h3{
    font-size: 14px;
    text-align: center;
    color: #333;
    font-weight:normal;
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
  }
  .goods-right .goods-right-content .goods-right-item .goods-price{
    color: #ff6700;
    font-size: 14px;
    text-align: center;
    margin:15px 0;
  }
  .goods-right .goods-right-content .goods-right-item .goods-rank{
    margin: 0 10px;
    font-size: 12px;
    text-align: center;
    text-overflow: ellipsis;
    white-space: nowrap;
    overflow: hidden;
    color: #b0b0b0;
  }
  .goods-right .goods-right-content .goods-right-item .review{
    position: absolute;
    left:0;
    bottom:0;
    width:234px;
    font-size:12px;
    line-height:18px;

    overflow: hidden;
    box-sizing: border-box;
    color:#fff;
    background:#ff6700;

  }
  .goods-right .goods-right-content .goods-right-item .review .review-content {
    display: block;
    text-align: center;
    margin: 8px 30px;
  }
  .goods-right .goods-right-content .goods-right-item .review .review-author{
    display: block;
    text-align: center;
    margin: 8px;
  }
  .fade2-enter-active{
    transition:all .5s;
    opacity:1;
    height:76px;
  }
  .fade2-enter{
    opacity:0;
    height:0;
  }

  .goods-right-small{
    width:234px;
    height:260px;
    /*background:lightgreen;*/
  }
  .goods-right-small .item-small{
    width:234px;
    height:143px;
    margin:0 0 14px 14px;
    padding:30px 0 0  30px;
    background:#fff;
    cursor: pointer;
    box-sizing:border-box;
  }
  .goods-right-small .item-small:hover{
    transform: translateY(-1px);
    box-shadow: 5px 5px 20px #ccc;
  }
  .goods-right-small .item-small div{
    float: left;
    margin-top:10px;
    width:80px;
    height:100%;
    margin-right:20px;
    /*background:red;*/
  }
  .goods-right-small .item-small h3{
    font-size:14px;
    text-align:center;
    color:#333;
    margin-bottom:20px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space:nowrap;

  }
  .goods-right-small .item-small span{
    display: block;
    width:100%;
    color:#ff6700;
    font-size:14px;
    text-align: center;
  }
  .goods-right-small .item-small img{
    float: left;
    width:80px;
    height:80px;
  }
  .icon-arrow{
    margin-top:5px;
    color:#ff6700;
  }
</style>
<script>
  export default({
    props: ['currGoods'],
    data(){
      return {
          isShow:false
      }
    },
    computed:{
      lastGoods:function () {
        if(this.currGoods && this.currGoods.length>0){
            return this.currGoods[this.currGoods.length-1];
        }else{
            return null;
        }
      }
    },
    methods:{
      evtGoodsEnter22:function (index) {
        this.currGoods[index].reviewStatus=true;
        console.log( this.currGoods[index].reviewStatus,'enter')
      },
      evtGoodsOut22:function (index) {
        this.currGoods[index].reviewStatus=false;
        console.log( this.currGoods[index].reviewStatus,'out')
      }
    }
  })
</script>
