/* 我的足迹 */
<template>
 <div class="container">
     <div class="box-browse">
         <img src="../../assets/images/browse.jpg" alt="">
        <p>你还没有浏览过商品，赶紧去浏览吧</p>
        <router-link tag="p" to="/">去逛逛</router-link>
     </div>
     
 </div>
</template>

<script>
export default {

}
</script>

<style lang='stylus' scoped>
.container
    background-color #f2f2f2;
    width 100%
    display flex
    flex-direction column
    .box-browse
        text-align center
        p   
            text-align center
            font-size 0.12rem
        p:nth-child(3) 
            margin 0 auto
            margin-top .24rem
            font-size .16rem
            border .01rem solid #ccc
            border-radius .04rem
            width 1rem
            padding 0.04rem
            background-color #fff
            

</style>