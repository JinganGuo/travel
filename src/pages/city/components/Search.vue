<template>
    <div>
        <div class="search">
            <input v-model="keyword" type="text" placeholder="请输入城市名或拼音">
        </div>
        <div class="search-content" ref="search" v-show="keyword">
            <ul>
                <li class="search-item border-bottom" 
                    v-for="(item, index) of list" 
                    :key="index"
                    @click="handleCityClick(item.name)"
                >{{item.name}}</li>
                <li class="search-item border-bottom" v-show="hasNoData">没有找到相关数据</li>
            </ul>
        </div>
    </div>

</template>

<script>
    import BScorll from 'better-scroll'
    export default {
        name: "CitySearch",
        data () {
            return {
               list: [], // 记录匹配的结果
               keyword: '',
               timer: null
            }
          
        },
        props: {
            cities: Object
        },
        methods: {
            handleCityClick (city) {
                this.$store.dispatch("changeCity", city)
                this.$router.push("/")
            }
        },
        computed: {
            hasNoData () {
                return !this.list.length
            }
        },
        watch: {
            keyword () {
                if (this.timer) {
                    clearTimeout(this.timer)
                }
                if(!this.keyword){
                    this.list = []
                    return
                }
                this.timer = setTimeout(() => {
                    const result = []
                    for(let i in this.cities) {
                        this.cities[i].forEach((value) => {
                            if(value.spell.indexOf(this.keyword) > -1 || 
                                value.name.indexOf(this.keyword) > -1) {
                                    result.push(value)
                                }
                        });
                    }
                    this.list = result
                } ,100)
            }
        },
        mounted () {
               this.scroll = new BScorll(this.$refs.search)
        }
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
    .search-content 
        position absolute
        z-index 1
        top 1.57rem
        bottom 0
        left  0 
        right 0 
        background #eee
        ul 
            .search-item 
                line-height .62rem
                padding-left .2rem
                background #ffffff
                color #666
</style>


