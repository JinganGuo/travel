<template>
    <div class="home">
        <home-header></home-header>
        <home-swiper :list="swiperlist"></home-swiper>
        <home-icons :icons="iconslist"></home-icons>
        <home-hotlist :hotlist="hotlist" :hottip="hottip"></home-hotlist>
        <home-favourate :favouratelist="favouratelist"></home-favourate>
        <home-weekend :weekendlist="weekendlist"></home-weekend>
        <home-footer></home-footer>
    </div>
</template>

<script>
    import HomeHeader from './components/Header'
    import HomeSwiper from './components/Swiper'
    import HomeIcons from './components/Icons'
    import HomeHotlist from './components/Hotlist'
    import HomeFavourate from './components/Favourate'
    import HomeWeekend from './components/Weekend'
    import HomeFooter from './components/Footer'
    import axios from 'axios'
    import { mapState } from 'vuex'

    export default {
        name: 'Home',
        components: {
            HomeHeader,
            HomeSwiper,
            HomeIcons,
            HomeHotlist,
            HomeFavourate,
            HomeWeekend,
            HomeFooter
        },
        data () {
            return {
                lastCity: '',
                swiperlist: [],
                iconslist: [],
                hotlist: [],
                hottip: [],
                favouratelist: [],
                weekendlist: []
            }
        },
        computed: {
            ...mapState(['city'])
        },
        methods: {
            getHomeInfo () {
                axios.get('/api/index.json?city=' + this.city)
                    .then(this.getHomeInfoSucc)
            },
            getHomeInfoSucc (res) {
                res = res.data
                if(res.ret && res.data) {
                    const data = res.data
                    this.swiperlist = data.swiperList
                    this.iconslist = data.iconList
                    this.hotlist = data.hotList
                    this.hottip = data.topImg
                    this.favouratelist = data.favourateList
                    this.weekendlist = data.weekendList
                }
            }
        },
        mounted () {
            this.lastCity = this.city
            this.getHomeInfo()
        },
        activated () {
            if(this.lastCity !== this.city) {
                this.lastCity = this.city
                this.getHomeInfo()
            }
        }
    }
</script>
     
       
<style lang="stylus" scoped>
    @import '../../assets/styles/varibles.styl'
    @import '../../assets/styles/mixins.styl'
   .home
        background: $bgGray
</style>

