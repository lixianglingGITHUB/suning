<template>

    <div class="foods">
            <van-pull-refresh
            v-model="isLoading"
            success-text="刷新成功"
            @refresh="onRefresh"
            >
            <van-list
                v-model="loading"
                @load="onLoad"
                :finished="finished"
                finished-text="duang 到底啦~"
            >
                <TableContent :foodcate="foodcate"></TableContent>
                <LimitedTimeSpike :goodsList="goodsList"></LimitedTimeSpike>
                <h5>为你推荐</h5>
                <GoodList :goodsList="goodsList"></GoodList>
            </van-list>
            </van-pull-refresh>


    </div>
</template>

<script>
import TableContent from "../../../components/TableContent.vue"
import LimitedTimeSpike from "../../../components/LimitedTimeSpike.vue"
import GoodList from "../../../components/GoodsLists.vue"
import { get } from "../../../utils/http.js"
import Vue from 'vue';
import { PullRefresh , List } from 'vant';
Vue.use(List)
Vue.use(PullRefresh);
export default {
    data() {
        return {
            goodsList:[],
            foodcate:[],
            isLoading: false,
            loading: false,
            finished: false,
        }
    },
    components:{
        TableContent,
        LimitedTimeSpike,
        GoodList,
    },
    created(){
        this.u = 6132551008,
        this.msCount = 20,
        this.catalogueId = '',
        this.flag = 1
    },
    beforeRouteEnter(to, from, next) {
        next(vm=>{
            vm.loadDataRoute(to.path)
        })
    },
    beforeRouteUpdate (to, from, next) {
        this.loadDataRoute(to.path)
        next()
    },
    // async mounted() {
    //     let result = await get({
    //         url:"/pdua/mpapi/pd/xcxTabPage.do?callback=callback",
    //         params:{
    //             flag:1,
    //             msCount:20,
    //             catalogueId:202275
    //         }
    //     })
    //     this.goodsList = JSON.parse(result.data.substring(9,result.data.length-2)).data.msSkus
    //     this.foodcate = JSON.parse(result.data.substring(9,result.data.length-2)).data.iconTags
        
    // },
    methods: {
        loadDataRoute(path){
            switch(path){
                case '/index/Goods/food':
                    this.catalogueId = 202275
                    this.impShow = true
                    break;
                case '/index/Goods/mumson':
                    this.catalogueId = 202261
                    this.impShow = true
                    break
                case '/index/Goods/appli':
                    this.catalogueId = 202251
                    this.impShow = true
                    break;
                case '/index/Goods/percare':
                    this.catalogueId = 202270
                    this.impShow = true
                    break
                case '/index/Goods/phone':
                    this.catalogueId = 202263
                    this.impShow = true
                    break;
                case '/index/Goods/checken':
                    this.catalogueId = 202250
                    this.impShow = true
                    break
                case '/index/Goods/duds':
                    this.catalogueId = 202252
                    this.impShow = true
                    break;
                case '/index/Goods/health':
                    this.catalogueId = 202253
                    this.impShow = true
                    break

                
            }
            this.loadData(this.catalogueId)
        },
        async loadData(){
            if(this.isLoading){
                this.foodcate = [],
                this.goodsList = [],
                this.u = 6132551008
                this.flag = 1
            }
            let result = await get({
                    url:"/pdua/mpapi/pd/xcxTabPage.do?callback=callback&cityCode=010",
                    params:{
                        u:this.u,
                        catalogueId:this.catalogueId,
                        flag:this.flag
                    }
                })
            this.goodsList =[
                ...this.goodsList,
                ...JSON.parse(result.data.substring(9,result.data.length-2)).data.msSkus
            ]
            // console.log(this.goodsList)
            this.foodcate = [
                ...JSON.parse(result.data.substring(9,result.data.length-2)).data.iconTags
            ]
            this.loading = false
            this.isLoading = false
            this.u++
            this.flag++
          
            if(this.u>6132551010) this.finished = true
        },
        onRefresh() {
            this.loadData()
        },
        onLoad(){
            this.loadData()
        },

    },
    watch: {
        $route(to){
            this.foodcate=[]
            this.goodsList=[]
        }
    },
}
</script>
<style lang="stylus" scoped>
.foods
    overflow-y scroll
    h5
        font-size 0.16rem
        color #000000
        background #eeeeee
        padding-left 0.2rem
        height 0.36rem
        padding-top 0.16rem
</style>