<template>
  <div class="video-container">
    <goods-header :title="title2" :is-show-more="true" :more-url="moreUrl"></goods-header>
    <div class="video-content">
      <ul>
        <li v-for="item in videos" @click="evtPlayVideo(item)">
          <div>
            <img :src="item.imgUrl" alt="">
            <span><i class="fa fa-play"></i></span>
          </div>
          <h3>{{item.title}}</h3>
          <p>
            {{item.desc}}
          </p>
        </li>
      </ul>
    </div>
  </div>
</template>
<style>
  .video-container {
    clear: both;
    width: 1226px;
    margin: 0 auto;
  }

  .video-content {
    width: 1226px;
    margin: 0 auto;
  }

  .video-content ul {
  }

  .video-content ul li {
    float: left;
    width: 296px;
    margin: 0 0 14px 14px;
    height: 285px;
    cursor: pointer;
    transition: all .3s;
    background: #fff;
  }

  .video-content ul li:first-child {
    margin-left: 0;
  }

  .video-content ul li:hover {
    transform: translateY(-3px)
  }

  .video-content ul li:hover div span {
    background: #ff6700;
  }

  .video-content ul li div {
    position: relative;
  }

  .video-content ul li span {
    position: absolute;
    display: block;
    left: 20px;
    bottom: 10px;
    width: 32px;
    height: 20px;
    line-height: 20px;
    color: #fff;
    text-align: center;
    font-size: 12px;
    border: 2px solid #fff;
    border-radius: 12px;
    background: #333;
  }

  .video-content ul li img {
    width: 296px;
    height: 180px;
  }

  .video-content ul li h3 {
    color: #333;
    font-size: 14px;
    font-weight: normal;
    text-align: center;
  }

  .video-content ul li p {
    height: 18px;
    margin: 0;
    font-size: 12px;
    text-align: center;
    color: #b0b0b0;
    margin-top: 10px;
  }
</style>
<script>
  import GoodsHeader from './common/GoodsHeader'
  export default({
    data(){
      return {
        title2: '内容',
        moreUrl: '',
        title: '视频',
        videos: [{
          videoUrl: 'http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1ODg5ODA0MA==',
          imgUrl: 'http://i3.mifile.cn/a4/73d67577-cbc7-4bd0-8678-4b1e95f4f4dc',
          title: '红米年度品牌视频',
          desc: '一亿人喜爱你，是一种责任。'
        },
          {
            videoUrl: 'http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1OTg3NjQ4OA==',
            imgUrl: 'http://i3.mifile.cn/a4/f7e434fb-8ce4-4442-bf78-0d66e409dfc3',
            title: '小米笔记本Air最全介绍视频',
            desc: '带独立显卡的轻薄笔记本'
          },
          {
            videoUrl: 'http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1OTg4NjY0OA==',
            imgUrl: 'http://i3.mifile.cn/a4/e2df3ad8-4147-44e1-8a54-b6bcafdc6c66',
            title: '小米笔记本Air可靠性测试视频',
            desc: '小米笔记本Air是如何炼成的？'
          },
          {
            videoUrl: 'http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTU2NDM3NjEzMg==',
            imgUrl: 'http://i3.mifile.cn/a4/T1v3LgBTxv1RXrhCrK.jpg',
            title: '小米Max 绝美外观视频',
            desc: '6.44" 大屏黄金尺寸，看什么都震撼'
          }]
      }
    },
    components: {
      GoodsHeader
    },
    methods: {
      evtPlayVideo: function (item) {
        var that=this;
        let videoOpt = {
          status: true,
          title: item.title,
          videoUrl: item.videoUrl
        }
        this.$emit('play',videoOpt);
//        console.log(videoOpt)
      }
    }
  })
</script>
