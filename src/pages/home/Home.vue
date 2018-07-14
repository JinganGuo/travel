<template>
    <div class="home">
        <home-header></home-header>
        <home-swiper></home-swiper>
        <home-icons></home-icons>
        <home-hotlist></home-hotlist>
        <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
        <div>aa</div>
    </div>
</template>

<script>
    import HomeHeader from './components/Header'
    import HomeSwiper from './components/Swiper'
    import HomeIcons from './components/Icons'
    import HomeHotlist from './components/Hotlist'
    export default {
        name: 'Home',
        components: {
            HomeHeader,
            HomeSwiper,
            HomeIcons,
            HomeHotlist
        }
    }
</script>
     
       
<style lang="stylus" scoped>
    @import '../../assets/styles/varibles.styl'
    @import '../../assets/styles/mixins.styl'
   .home
        background: $bgGray
</style>

