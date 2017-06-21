<template>
  <div class="top-sub">
    <div class="sub-l">
      <ul>
        <li>
          <a href="">
            <i class="fa fa-mobile fa-fw sub-icon"></i>
            <p>选购手机</p>
          </a>
        </li>
        <div class="line-vertical"></div>
        <li>
          <a href="">
            <i class="fa fa-mobile fa-fw sub-icon"></i>
            <p>选购手机</p>
          </a>
        </li>
        <div class="line-vertical"></div>
        <li>
          <a href="">
            <i class="fa fa-mobile fa-fw sub-icon"></i>
            <p>选购手机</p>
          </a>
        </li>
        <div class="line-horizontal">
        </div>
        <div class="line-horizontal">
        </div>
        <div class="line-horizontal">
        </div>
        <li>
          <a href="">
            <i class="fa fa-mobile fa-fw sub-icon"></i>
            <p>选购手机</p>
          </a>
        </li>
        <div class="line-vertical"></div>
        <li>
          <a href="">
            <i class="fa fa-mobile fa-fw sub-icon"></i>
            <p>选购手机</p>
          </a>
        </li>
        <div class="line-vertical"></div>
        <li>
          <a href="">
            <i class="fa fa-mobile fa-fw sub-icon"></i>
            <p>选购手机</p>
          </a>
        </li>
      </ul>
    </div>
    <ul class="subs">
      <li>
        <a href="http://hd.mi.com/y/08191p/index.html" target="_blank">
          <img src="http://i3.mifile.cn/a4/1327d707-4f67-4c36-8ae5-3d7704c989eb" alt="" />
        </a>
      </li>
      <li>
        <a href="http://item.mi.com/buyphone/redmipro/" target="_blank">
          <img src="http://i3.mifile.cn/a4/c202123c-4197-4666-9793-2f1e156ab23a" alt="" />
        </a>
      </li>
      <li>
        <a href="http://item.mi.com/static/buymipad" target="_blank">
          <img src="http://i3.mifile.cn/a4/216f7f38-66ee-4c1b-8409-8d77cb64d386" alt="" />
        </a>
      </li>
    </ul>
  </div>
</template>
<style>
  .top-sub {
    position: relative;
    width: 1226px;
    height: auto;
    margin: 14px auto 26px;


  }

  .top-sub .sub-l {

    float: left;
    width: 234px;
    height: 170px;
    background: #5f5750;
    /*border:1px solid red;*/
  }

  .top-sub .sub-l ul {
    display: flex;
    flex-flow: row wrap;
    justify-content: flex-start;
    align-items: flex-start;
    padding: 3px;
  }

  .top-sub .sub-l ul li {
    width: 75px;
    height: 82px;
    cursor: pointer;
    /*border:1px solid red;*/
  }

  .top-sub .sub-l ul li:hover .sub-icon {
    color: #fff;
  }

  .top-sub .sub-l ul li:hover p {
    color: #fff;
  }
  .top-sub .sub-l ul li p{
    display: block;
    width:75px;
    font-size:12px;
    text-align:center;
    color: rgba(255, 255, 255, 0.7);
    margin:0;

  }
  .top-sub .sub-l ul li i.sub-icon {
    width: 75px;
    height: 24px;
    margin-top: 18px;
    margin-bottom: 5px;
    font-size: 20px;
    color: rgba(255, 255, 255, 0.7);
  }
  .line-vertical {
    width: 1px;
    height: 60px;
    margin-top: 10px;
    background: rgba(255,255,255,0.1);
  }
  .line-horizontal {
    width: 60px;
    height: 1px;
    margin: 0 8px;
    background: rgba(255,255,255,0.1);
  }
  .subs{
    display: flex;
    flex-flow:row nowrap;
    justify-content: flex-start;

  }
  .subs li{
    width:316px;
    height:170px;
    margin-left:15px;
  }
  .subs li a{
    display: block;

  }
  .subs li a:hover{
    box-shadow:0 5px 30px #ccc;
  }
  .subs li a img{
    display: block;
    width:316px;
    height:170px;
  }

</style>
<script>
  export default({
    data(){
      return {}
    }
  })
</script>
