<template>
    <div class="container">
        
    </div>
</template>

<script>
    export default {
        name: "CommonGallary"
    }    
</script>

<style lang="stylus" scoped>
    .container
        display flex
        flex-direction column
        justify-content center
        z-index 999
        position fixed
        left 0 
        right 0
        top 0
        bottom 0
        background #000
        .wrapper 
            overflow hidden
            width 100%
            height 0
            padding-bottom  100%
            
</style>
