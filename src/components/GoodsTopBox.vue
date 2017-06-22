<template>
    <div class="boxs-container ">
      <div class="boxs clearfix">
        <goods-header :title="'智能硬件'" :is-show-more="true" :more-url="moreUrl"></goods-header>
  <!--      <div class="boxs-top">
          <h3>只能硬件</h3>
          <a href="">
            <span>查看全部
                <i class="fa fa-chevron-circle-right fa-fw"></i>
            </span>
          </a>
        </div>-->
        <div class="boxs-content clearfix">
          <div class="box-left">
            <a href="http://www.mi.com/scooter/" target="_blank">
              <img src="http://i3.mifile.cn/a4/124d82cc-cfce-44ab-b711-28b21be81683" alt="" />
            </a>
          </div>
          <div class="box-right">
            <ul>
              <li v-for="good in goods">
                <span  :class="good.discountType">{{good.discount}}</span>
                <a href="">
                  <img :src="good.imgUrl" alt="">
                  <h3>{{good.title}}</h3>
                </a>
                <p class="box-desc">
                  {{good.desc}}
                </p>
                <p class="box-price">
                  {{good.price}}元
                  <span class="old-price">
                    {{good.oldPrice}}元
                  </span>
                </p>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
</template>
<style scoped="">
  .boxs-container{
    width:1226px;
    height:auto;
    margin:0 auto;
    padding-top: 60px;
    margin-bottom: 26px;
    background: #f5f5f5;
  }
  .boxs{
    position: relative;
    width:1226px;
    height:auto;
    margin:0 auto;
  }
 /* .boxs-top{
    width:100%;
    height:58px;
    line-height:58px;
    !*border:1px solid red;*!
  }
  .boxs-top h3{
    float: left;
    margin:0;
    font-size:22px;
    font-weight:200;
    line-height:58px;
    color:#333;
  }

  .boxs-top span{
    float: right;
    color:#424242;
    font-size:16px;
    display: block;
    cursor: pointer;
  }
  .boxs-top span i{
    color:#b0b0b0;
    font-size:20px;
  }
  .boxs-top span:hover{
    color:#ff6700;
  }
  .boxs-top span:hover i{
    color:#ff6700;
  }*/
  .box-right img {
    display: block;
    width: 160px;
    height: 160px;
    margin: 0 auto;
  }
  .box-left{
    float: left;
    width:234px;
    height:614px;
    cursor: pointer;
  }
  .box-left:hover{
    transform:translateY(-10px);
    box-shadow:5px 5px 20px #ccc;
  }
  .box-right{
    float: left;
    width:992px;
    height:628px;
  }
  .box-right ul{
    float: left;
    display:flex;
    flex-flow:row wrap;
    justify-content: flex-start;
    width:100%;
    height:100%;
    background:#f5f5f5;
  }
  .box-right ul li{
    position: relative;
    margin:0 0 14px 14px;
    padding:20px 0;
    width:234px;
    height:260px;
    background: #fff;
  }
  .box-right ul li:hover{
    transform:translateY(-1px);
    box-shadow:5px 5px 20px #ccc;
  }
  .box-right ul li>span{
    position: absolute;
    top:0;
    left:50%;
    width:64px;
    height:20px;
    line-height:20px;
    margin-left:-32px;
    font-size:12px;
    text-align:center;
    color:#fff;
    z-index:4;
  }
  .box-right ul li>span.free{
    background-color: #ffac13;
  }
  .box-right ul li>span.new{
    background-color: #83c44e;
  }
  .box-right ul li>span.discount{
    background-color: #e53935;
  }
  .box-right ul li> a h3{
    font-size:14px;
    text-align:center;
    color:#333;
    font-weight:normal;
  }
  .box-right ul li .box-desc{
      margin:15px 10px;
    height:18px;
    font-size:12px;
    text-align:center;
    -ms-text-overflow: ellipsis;
    text-overflow: ellipsis;
    white-space:normal;
    overflow: hidden;
    color:#b0b0b0;
  }
  .box-right ul li .box-price{
    color:#ff6700;
    font-size:14px;
    text-align:center;
  }
  .box-right ul li .box-price .old-price {
    color: #b0b0b0;
    text-decoration: line-through;
  }
</style>
<script>
  import GoodsHeader from './common/GoodsHeader'
    export default({
      data () {
        return {
            moreUrl:'',
          goods: [
            {sourceUrl: '//item.mi.com/1161200059.html', imgUrl: 'http://i3.mifile.cn/a4/T1rQAgB7Av1RXrhCrK.jpg', title: '小米路由器3', desc: '四天线设计，更安全更稳定', price: '149', discountType: 'free', discount: '免邮费'},
            {sourceUrl: '//www.mi.com/mibicycle/', imgUrl: 'http://i3.mifile.cn/a4/2b69b930-a2fd-4d09-a46a-8690cb79f764', title: '电助力折叠自行车', desc: '力矩传感电助力，让城市出行轻松有趣', price: '149', discountType: 'new', discount: '新品'},
            {sourceUrl: '//www.mi.com/mitu/', imgUrl: 'http://i1.mifile.cn/a1/pms_1464615180.86261317!220x220.jpg', title: '米兔智能故事机', desc: '能说会道，宝宝的好玩伴', price: '199', discountType: 'new', discount: '新品'},
            {sourceUrl: '//www.mi.com/water2/', imgUrl: '//i3.mifile.cn/a4/T1zTK_Bbhv1RXrhCrK.jpg', title: '小米净水器', desc: '厨下式 RO反渗透直出纯净水，包邮包安装', price: '1999'},
            {sourceUrl: '//www.mi.com/ihealth/ ', imgUrl: 'http://i1.mifile.cn/a1/T17FCQByWv1RXrhCrK!220x220.jpg', title: 'iHealth智能血压计（蓝牙版）', desc: '送给父母的健康礼物 测血压仅需1步', price: '199'},
            {sourceUrl: '//www.mi.com/dianfanbao/', imgUrl: 'http://i1.mifile.cn/a1/T1OVC_ByY_1RXrhCrK!220x220.jpg', title: '米家压力IH电饭煲', desc: '智能烹饪，3L 容量', price: '999'},
            {sourceUrl: '//item.mi.com/1163200015.html', imgUrl: 'http://i1.mifile.cn/a1/pms_1470730028.12443689!220x220.jpg', title: '全系智能套装限时款', desc: '开启你的智能生活', price: '292', oldPrice: '325', discountType: 'discount', discount: '享九折'},
            {sourceUrl: '//list.mi.com/accessories/tag?id=guangganban', imgUrl: 'http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99'}
          ]
        }
      },
      components:{
        GoodsHeader
      }
    })
</script>
