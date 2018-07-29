<template>
    <div class="banner">
        <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1609/7a/7ae8ee7831836095a3.water.jpg_600x330_5d562f69.jpg" alt="banner">
        <div class="banner-info">
            <div class="banner-title">金海湖风景区</div>
            <div class="banner-number">
                <span class="iconfont banner-icon">&#xe624;</span>
                5
            </div>
        </div>
        <common-gallary></common-gallary>
    </div>
</template>

<script>
    import CommonGallary from 'common/gallary/Gallary'
    export default {
        name: "DetailBanner",
        components: {
            CommonGallary
        }
    }
</script>

<style lang="stylus" scoped>
    .banner
        overflow hidden
        height 0
        padding-bottom 55%
        position relative
        .banner-img
            width 100% 
        .banner-info
            display flex
            position absolute
            left 0
            right  0
            bottom  0
            line-height .6rem
            color  #ffffff
            background-image linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8))
            .banner-title
                flex 1
                font-size .32rem
                padding 0 .2rem
            .banner-number 
                padding 0 .4rem
                line-height .4rem
                height  .32rem
                margin-top .14rem
                border-radius .32rem
                font-size .24rem
                background rgba(0, 0, 0, .9)
                .banner-icon 
                    font-size .24rem
            

</style>

