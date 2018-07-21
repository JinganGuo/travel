<template>
    <div class="search">
        <input type="text" placeholder="请输入城市名或拼音">
    </div>
</template>

<script>
    
    export default {
        name: "CitySearch"
    }
</script>

<style lang="stylus" scoped>
     @import '../../../assets/styles/varibles.styl'

    .search
        height .72rem
        padding 0 .1rem
        background $bgColor
        input 
            width 100%
            box-sizing border-box
            padding 0 .1rem 
            text-align center
            border-radius .1rem
            height .62rem
            line-height .62rem
            color #666
</style>


