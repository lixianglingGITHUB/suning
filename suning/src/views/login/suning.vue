<template>
  <div class="contianer">
    <div class="header">
      <div class="tit">
        <span>我的易购</span>
        <a href=""></a>
      </div>

      <div class="login-user">
          <div class="img">
            <i class="yo-ico">&#xe611;</i>
            <!-- <img src="https://image.suning.cn/uimg/cmf/cust_headpic/0000000000_01_240x240.jpg" alt=""> -->
          </div>
          <div class="login">登录/注册</div>
      </div>
    </div>
    <div class="main">
      <div class="box-title">
        <span>我的订单</span>
        <a>
          查看全部
          <i class="to-all"></i>
        </a>
      </div>
      <div class="box-order">
        <a>
          <div>
            <i class="pay-ico"></i>
            <p>待支付</p>
          </div>
        </a>
        <a>
          <div>
            <i class="recieve-ico"></i>
            <p>待收货</p>
          </div>
        </a>
        <a>
          <div>
            <i class="comment-ico"></i>
            <p>评价有礼</p>
          </div>
        </a>
        <a>
          <div>
            <i class="maintain-ico"></i>
            <p>退换/售后</p>
          </div>
        </a>
        <a>
          <div>
            <i class="order-ico"></i>
            <p>常购清单</p>
          </div>
        </a>  
      </div>
    </div>

    <div class="guess">
        <div class="nav">
          <router-link tag="span" to="/recommend"  active-class="active">好货推荐</router-link>
          <router-link tag="span" to="/footprint"  active-class="active">我的足迹</router-link>
        </div>
        <router-view></router-view>
    </div>
  </div>
</template>

<script>
export default {};
</script>


<style lang="stylus">
.contianer  
  background-color #f2f2f2;
  width 100%
  height 100%
  display flex
  flex-direction column
  overflow-y scroll
  .header
    width 100%
    height 1.8rem 
    background-color #FFDB47; 
    .tit
      display flex
      margin-top .1rem
      span  
        flex 1
        font-size .18rem
        font-weight bold
        text-align center
      a 
        background: url(https://res.suning.cn/project/msinode/wap/home/image/setting.png) no-repeat center;
        background-size: contain;
        display: block;
        width: .18rem;
        height: .18rem;
        margin-right .18rem
    .login-user
      width 100%
      height .8rem
      margin-top .24rem
      display flex
      align-items: center;
      justify-content: center;
      .img 
        width .7rem
        height .7rem
        border-radius .7rem
        margin-left .24rem
        background-color #eee
        display flex 
        align-item center
        justify-content: center;
        i 
          font-size .36rem
          color #ccc
          margin-top .08rem

      .login 
        padding-left .24rem
        flex 1
        font-size .12rem
  .main
    background-color #ffffff
    margin .12rem
    height 1.2rem
    border-radius .12rem
    padding .12rem
    .box-title
      display flex
      span
        flex 1 
        font-size .16rem
        font-weight bold
      a 
        font-size .12rem
        .to-all
          display: inline-block;
          width: .14rem;
          height: .14rem;
          background: url(https://res.suning.cn/project/msinode/wap/home/image/next.png) no-repeat;
          background-size: contain;
    .box-order
      display flex
      height .5rem
      width 100%
      a       
        display flex
        flex 1 
        margin-top .14rem  
        div 
          flex 1
          color #444
          height 0.8rem
          text-align center
          line-height 0.26rem
          i 
            font-size 0.24rem
            display: block;
            width: .4rem;
            height: .32rem;
            margin-left .16rem
          p
            font-size 0.14rem
            color #666
          .pay-ico
            background: url(https://res.suning.cn/project/msinode/wap/home/image/order-icon01.png) no-repeat;
            background-size: contain;
          .recieve-ico
            background: url(https://res.suning.cn/project/msinode/wap/home/image/order-icon02.png) no-repeat;
            background-size: contain;
          .comment-ico
            background: url(https://res.suning.cn/project/msinode/wap/home/image/order-icon03.png) no-repeat;
            background-size: contain;
          .maintain-ico
            background: url(https://res.suning.cn/project/msinode/wap/home/image/order-icon04.png) no-repeat;
            background-size: contain;
          .order-ico
            background: url(https://res.suning.cn/project/msinode/wap/home/image/order-icon05.png) no-repeat;
            background-size: contain;

  .guess
    width 100%
    .nav
      height .42rem
      line-height .42rem
      background-color #fff
      display flex
      margin-bottom .12rem
      span 
        flex 1
        font-size .16rem
        text-align center
      .active
        font-weight bold 

</style>