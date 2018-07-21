<template>
    <div class="header">
              城市选择
            <router-link to="/">
                <span class="iconfont back-icon">&#xe624;</span>
            </router-link>
            
       
         
    
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
        text-align center
        position relative
        font-size .32rem
        a 
            color: #ffffff
            span 
                position absolute 
                top: 0 
                left .1 rem
        
          
</style>


