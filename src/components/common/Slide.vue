<template>
  <div class="banner">
    <span  @click="slidePre" class="slide-pre"><i class="fa fa-chevron-left fa-2x "></i></span>
    <span @click="slideNext" class="slide-next"><i class="fa fa-chevron-right fa-2x "></i></span>

      <div v-for="(item,index) in banners" class="slide" 	>
        <transition name="fadeSlide">
        <a :href="item.sourceUrl" target="_blank" v-show="index === curpage">
          <img :src="item.imgUrl" alt="">
        </a>
        </transition>
      </div>

  </div>
</template>
<style>
  .banner {
    position: relative;
    width: 1226px;
    height: 460px;
    z-index: 0;
  }
  .banner>span{
    display: block;
    position: absolute;
    top:50%;
    width:40px;
    height:70px;
    z-index: 10;
    margin-top:-35px;
    cursor: pointer;
  }
  .banner>span:hover{
    background:rgba(0,0,0,0.3);
  }
  .banner>span.slide-pre{
    left:235px;
  }
  .banner>span.slide-next{
    right:0;
  }
  .banner .slide{
    position: absolute;
    left:0;
    top:0;
    width:1226px;
    height:460px;
    /*transition:all 0.3s;*/
  }
  .banner .slide img{
    width:100%;
    height:100%;
  }
  .banner .fa{
    position: relative;
    left:50%;
    top:50%;
    width:30px;
    height:30px;
    margin-left:-15px;
    margin-top:-15px;
    color:#ecf0f1;
  }
  .fadeSlide-enter-active{
    transition:all .3s ease;
    opacity:1;
  }
  .fadeSlide-enter{
    opacity:0.3;
  }
</style>
<script>
  export default({
    props: ['banners'],
    data(){
      return {
        prevTid: '',
        curpage: 0,
        slideDirection: 1
      }
    },
    created:function () {
      this.slideAuto();
    },
    methods:{
      slidePre:function () {
        const lastPage=this.banners.length-1;
        if(this.curpage>0){
            this.curpage-=1;
        }else{
            this.curpage=lastPage;
        }
      },
      slideNext:function () {
        const lastPage=this.banners.length-1;
        if(this.curpage<lastPage){
          this.curpage+=1;
        }else{
          this.curpage=0;
        }
      },
      slideAuto:function () {
        clearInterval(this.prevTid);
        var that=this;
        this.prevTid=setInterval(function () {
          that.slideNext();
        },2000)
      }
    }
  })
</script>
