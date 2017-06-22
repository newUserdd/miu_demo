<template>
  <div class="content" :class="content.type">
    <h3>{{content.title}}</h3>
    <div class="slide-wrap">
      <span class="slide-pre" @click.stop="slidePre"><i
        class="fa fa-chevron-left fa-fw icon-chevron-left"></i></span>
      <span class="slide-next" @click.stop="slideNext"><i
        class="fa fa-chevron-right fa-fw icon-chevron-left"></i></span>
      <ul class="sub-content" :style="{'margin-left':currPage*(-299)+'px'}">
        <li v-for="item in content.list">
          <a :href="item.sourceUrl" target="_blank">
            <h3>{{item.title}}</h3>
            <p>{{item.desc}}</p>
            <img :src="item.imgUrl" alt="">
          </a>
        </li>
      </ul>
      <ul class="dot-list">
        <li v-for="(itme ,index) in content.list" :class="{active:currPage==index}">
          <span></span>
        </li>
      </ul>
    </div>
  </div>
</template>
<style>
  .content {
    position: relative;
    float: left;
    width: 296px;
    height: auto;
    margin: 0 0 14px 14px;
    padding-top: 45px;
    background: #fff;
    transition: all .3s;
  }

  .content > h3 {
    margin: 0 10px 18px;
    font-size: 16px;
    font-weight: 400;
    text-align: center;
  }

  .book {
    border-top: 1px solid #ffac13;
  }

  .book > h3 {
    color: #ffac13;
  }

  .theme {
    border-top: 1px solid #83c44e;
  }

  .theme > h3 {
    color: #83c44e;
  }

  .game {
    border-top: 1px solid #e53935;
  }

  .game > h3 {
    color: #e53935;
  }

  .app {
    border-top: 1px solid #2196f3;
  }

  .app > h3 {
    color: #e53935;
  }

  .content:hover {
    transform: translateY(-1px);
    box-shadow: 5px 5px 20px #ccc;
  }

  .content:hover .slide-wrap > span {
    opacity: 1;
  }

  .content:nth-child(1) {
    margin-left: 0;
  }

  .slide-wrap {
    width: 296px;
    height: 340px;
    overflow: hidden;
  }

  .slide-wrap .sub-content {
    width: 1200px;
    height: 340px;
    transition: all .5s;
  }

  .slide-wrap .sub-content li {
    position: relative;
    float: left;
    width: 296px;
    height: 340px;
  }

  .slide-wrap .sub-content li h3 {
    margin: 0 0 10px 0;
    font-weight: normal;
    font-size: 20px;
    text-align: center;
    color: #333;
  }

  .slide-wrap .sub-content li p {
    font-size: 12px;
    line-height: 1.5;
    text-align: center;
    color: #b0b0b0;
    width: 200px;
    margin: 0 auto 10px;
  }

  .slide-wrap .sub-content li img {
    display: block;
    width: 216px;
    height: 154px;
    margin: 0 auto;
  }

  .slide-wrap > span {
    display: block;
    width: 20px;
    height: 46px;
    line-height: 46px;
    font-size: 15px;
    text-align: center;
    margin-top: -24px;
    cursor: pointer;
    z-index: 11;
    background: #b0b0b0;
    color: #fff;
  }

  .slide-pre {
    position: absolute;
    left: 0;
    top: 50%;
    opacity: 0;
    transition: all 0.3s;
  }

  .slide-next {
    position: absolute;
    right: 0;
    top: 50%;
    opacity: 0;
    transition: all 0.3s;
  }

  .dot-list {
    display: block;
    position: absolute;
    left: 50%;
    bottom: 10px;
    margin-left: -70px;
    z-index: 11;
  }

  .dot-list li {
    display: inline-block;
    width: 10px;
    height: 10px;
    padding: 10px;
    margin: 0 2px;
    cursor: pointer;
  }

  .dot-list li.active span {
    background: #fff;
    border: 2px solid #ff6700;
  }

  .dot-list li span {
    display: block;
    width: 6px;
    height: 6px;
    border: 2px solid #f5f5f5;
    border-radius: 6px;
    text-indent: -9999em;
    overflow: hidden;
    background: #b0b0b0;
    transition: all .5s;
  }
</style>
<script>

  export default({
    props: ['content'],
    data(){
      return {
        currPage: 0
      }
    },
    methods: {
      slidePre: function () {
        if (this.currPage != 0) {
          this.currPage--;
        }
      },
      slideNext: function () {
        if (this.currPage < Math.floor((this.content.list.length - 1))) {
          this.currPage++;
        }
      }
    }
  })
</script>
