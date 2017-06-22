<template>
  <header class="top-container">
    <div class="top-bar">
      <div class="topbar-nav">
        <ul>
          <li v-for="item in navs">
            <a :href="item.sourceUrl" v-if="item.name=='小米商城'">{{item.name}}</a>
            <a :href="item.sourceUrl" v-if="item.name!='小米商城'" target="_blank">{{item.name}}</a>
            <span>|</span>
          </li>
        </ul>
      </div>
      <div class="topbar-info">
        <a href="http://order.mi.com/site/login?redirectUrl=http://www.mi.com/index.html">登陆</a>
        <span>|</span>
        <a href="https://account.xiaomi.com/pass/register">注册</a>
      </div>
      <div class="topbar-cart" @mouseenter="evtCartEnter"@mouseleave="evtCartOut">
        <div class="cart"  :class="{'active': cartStatus}">
          <i class="fa fa-cart-arrow-down icon-cart"></i>
          <a href="">
            购物车(<span>1</span>)
          </a>
        </div>
        <transition name="fade" >
          <div class="cart-list"  v-if="cartStatus">
            购物车中还没有商品，赶快选购吧！
          </div>
        </transition>
      </div>
    </div>
  </header>
</template>
<style scoped="">
  .top-container{
    width:100%;
    height:40px;
    background:#333;
  }
  .top-bar{
    width:1266px;
    margin:0 auto;
    font-size: 12px;
    position: relative;
  }
  .top-bar .topbar-nav{
    float: left;
    height:40px;
    line-height:40px;
    overflow: hidden;
  }
  .top-bar .topbar-nav ul{

  }
  .top-bar .topbar-nav ul li{
    display: inline-block;
    height:40px;
    padding-left:5px;
  }
  .top-bar .topbar-nav ul li:hover a{
    color:#fff;
  }
  .top-bar .topbar-nav ul li a{
    color:#b0b0b0;
  }
  .top-bar .topbar-nav ul li span{
    display: inline-block;
    color:#b0b0b0;
    margin-left:5px;
  }
  .top-bar .topbar-nav ul li:last-child span{
    display: none;
  }
  .topbar-info{
    position: absolute;
    top:0;
    right:140px;
    height:40px;
    line-height:40px;
  }
  .topbar-info a{
    color:#b0b0b0;
  }
  .topbar-info span{
    color:#b0b0b0;
    margin:0 3px;
  }
  .topbar-info a:hover{
    color:#fff;
  }

  .topbar-cart{
    float: right;
    width:120px;
    height:40px;
    line-height:40px;
    text-align:center;
    background:#424242;
    cursor: pointer;
    position: relative;
  }
  .topbar-cart:hover{
    background:#fff;
  }
  .topbar-cart:hover a,.topbar-cart:hover .icon-cart,.topbar-cart:hover span{
    color:#ff6700;
  }
  .topbar-cart .active{
    background:#fff;
  }
  .topbar-cart .active a{
    color:#ff6700;
  }
  .topbar-cart a{
    display: block;
    width:100%;
    height:100%;
    color:#b0b0b0;
    padding-left:30px;
    box-sizing: border-box;
  }
  .topbar-cart .icon-cart{
    position: absolute;
    left: 20px;
    top: 10px;
    color: #b0b0b0;
    font-size: 20px;
  }
  .cart-list{
    position: absolute;
    right:0;
    top:39px;
    width:316px;
    height:96px;
    line-height:96px;
    text-align:center;
    background:#fff;
    box-shadow:0 0 5px #ccc;
    z-index:10;
    overflow: hidden;
  }

  .fade-enter-active {
    transition: all .5s;
    height:96px;
  }
  .fade-enter{
    opacity: 0;
    height:0;
  }
</style>
<script>
  export default({
    data(){
      return {
        navs: [
          {name: '小米商城', sourceUrl: 'http://www.mi.com/index.html'},
          {name: 'MIUI', sourceUrl: 'http://www.miui.com/'},
          {name: '米聊', sourceUrl: 'http://www.miliao.com/'},
          {name: '游戏', sourceUrl: 'http://game.xiaomi.com/'},
          {name: '多看阅读', sourceUrl: 'http://www.duokan.com/'},
          {name: '云服务', sourceUrl: 'https://i.mi.com/'},
          {name: '小米网移动版', sourceUrl: 'http://www.mi.com/c/appdownload/'},
          {name: '问题反馈', sourceUrl: 'http://static.mi.com/feedback/'},
          {name: 'Select Region', sourceUrl: 'http://www.mi.com/index.html'}
        ],
        timer: '',
        cartStatus: false
      }
    },
    methods:{
      evtCartEnter:function () {
        this.cartStatus=true;
        clearInterval(this.timer)
      },
      evtCartOut:function () {
        let self = this
        this.timer = setTimeout(function () {
          self.cartStatus = false
        }, 300)
      }
    }
  })
</script>
