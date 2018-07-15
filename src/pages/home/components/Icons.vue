<template>
    <div class="icon-container">
        <!-- 图标导航栏 -->
        <swiper :options="swiperOption">
             <swiper-slide class="icon-page" v-for="(page, index) of pages" :key="index">
                <div class="icon-item" v-for="item of page" :key="item.iconId">
                    <img class="icon-img" :src="item.iconUrl" :alt="item.iconIntr">
                    <p>{{item.iconIntr}}</p>
                </div>
             </swiper-slide>
             <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
        <!-- 定位、玩水季 -->
        <div class="position">
            <div class="position-left">
                <span class="iconfont">&#xe604;</span>
                定位失败
            </div>
            <div class="position-right">
                <span class="iconfont">&#xe689;</span>
                玩水季
            </div>
        </div>

        <!-- 广告 -->
        <ul class="ad-ul">
            <li class="ad-ul-left">
                <a href="#">
                    <img src="http://img1.qunarzz.com/piao/fusion/1806/29/30427c0e0658b502.png" alt="">
                </a>
            </li>
            <li>
                 <a href="#">
                    <img src="http://img1.qunarzz.com/piao/fusion/1806/36/e89032c5f7714f02.png" alt="">
                </a>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'HomeIcons',
        props: {
            icons: Array
        },
        data: function(){
            return {
                swiperOption: {
                    pagination: '.swiper-pagination',
                    loop: false
                }
            }
        },
        computed: {
            pages () {
                const pages = []
                this.icons.forEach((item, index) => {
                    const page = Math.floor(index / 8)
                    if(!pages[page]) {
                        pages[page] = []
                    }

                    pages[page].push(item)
                })
                return pages
            }
        }
    }
</script>

<style lang="stylus" scoped>
    @import '../../../assets/styles/varibles.styl'
     @import '../../../assets/styles/mixins.styl'

    .icon-container >>> .swiper-pagination
        position: static
        padding: .2rem 0
    .icon-container >>> .swiper-container
        background: $bgWhite
    .icon-container >>> .swiper-pagination-bullet-active
        background: rgba(0,175,190,.8) 
    .icon-container >>> .swiper-pagination-bullet
        height: 6px
        width: 6px

    .icon-container
        background: $bgGray
        .icon-page
            width: 100%
            background: $bgWhite
            box-sizing: border-box
            padding-top: .2rem
            display: flex
            flex-wrap: wrap
            .icon-item
                width: 25%
                text-align: center
                box-sizing: border-box
                padding-top: .15rem
                .icon-img
                    width: 55px
                    height: 55px
                p
                    padding-top: .1rem
                    ellipsis()
        .position
            display: flex
            background: $bgWhite
            border-top: 1px solid $bgGray
            div
                flex: 1
                text-align: center
                line-height: .98rem
            .position-left
                border-right: 1px solid $bgGray
        .ad-ul
            background: $bgWhite
            display: flex
            margin-top: .2rem 
            li
                flex: 1
                text-align: center
                height 1.4rem 
                img
                    // width: 100%
                    height 100%
            .ad-ul-left
                border-right: 1px solid $bgGray
</style>

