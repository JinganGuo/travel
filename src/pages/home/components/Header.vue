<template>
    <div class="header">
        <div class="header-left">
            <span class="iconfont back-icon">&#xe624;</span>
        </div>
        <div class="header-input">
             <span class="iconfont">&#xe632;</span>
            输入城市/景点/游玩主题
        </div>
        <div class="header-right">
            <span>成都</span>
            <span class="iconfont select-city-arrow-down">&#xe60c;</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'HomeHeader'
    }
</script>

<style lang="stylus" scoped>
    @import '../../../assets/styles/varibles.styl';
    .header
        display: flex
        line-height: .86rem
        background: $bgColor 
        color: #fff
        .header-left
            width: .64rem
            float: left 
            text-align: center
            .back-icon
                display: block
                font-size: .38rem
        .header-input
            flex: 1
            height: .62rem
            line-height: .62rem
            padding-left: .2rem
            margin-top: .12rem
            margin-left: .2rem
            background: #ffffff
            border-radius: .1rem
            color: #ccc
        .header-right
            width: 1.24rem
            float: right 
            text-align: center
            .select-city-arrow-down
                margin-left: -.08rem
</style>


