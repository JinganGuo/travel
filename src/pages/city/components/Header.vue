<template>
    <div class="header">
        <router-link to="/">
            <div class="header-left">
            <span class="iconfont back-icon">&#xe624;</span>
            </div>
        </router-link>

        <div class="header-title">
            城市选择
        </div>
    </div>
</template>

<script>
    
    export default {
        name: "CityHeader"
    }
</script>

<style lang="stylus" scoped>
     @import '../../../assets/styles/varibles.styl';
    .header
        
        line-height: .86rem
        background: $bgColor 
        color: #fff
        a 
            color: #ffffff
        .header-left
            width: .64rem
            float: left 
            text-align: center
            .back-icon
                display: block
                font-size: .38rem
        .header-title 
            text-align center
            font-size .34rem
</style>


