/* 我的推荐 */
<template>
 <div class="container">
     <div class="list">
         <ul>
            <li>
                 <img src="https://imgservice.suning.cn/uimg1/b2c/image/8LsubfbbXW30JE0sWa2b0A.jpg?from=mobile" alt="">
                 <p class="like-name">Apple AirPods 二代 配充电盒 Apple蓝牙耳机...</p>
                 <p class="like-price">￥998.00</p>
             </li>
             <li>
                <img src="https://imgservice.suning.cn/uimg1/b2c/image/9ZPxRv69z0bMyvqBnPh1Dg.jpg?from=mobile" alt="">
                 <p class="like-name">Apple iPhone 11 128G 白色 移动联通电信4G全网通...</p>
                 <p class="like-price">￥4999.00</p>
             </li>
             
         </ul>        
     </div>
 </div>
</template>

<script>
export default {

}
</script>

<style lang='stylus' scoped>
.contianer  
  background-color #f2f2f2;
  width 100%
  flex-direction column
  .list
    margin .12rem
    ul
        display flex
        li
            flex 1
            width width 2.2rem
            background-color #fff   
            height 2.2rem
            margin 0 .12rem
            img 
                width 1.5rem
                height 1.4rem
            .like-name 
                font-size .12rem
            .like-price
                font-size .14rem
                color red
</style>