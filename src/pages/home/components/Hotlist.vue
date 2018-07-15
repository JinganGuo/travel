<template>
    <div class="hotlist">
        <header>
            <div class="header-left">
                <img src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png" alt="">
                <h3>本周热门榜单</h3>
            </div>
            <div class="header-right">
                全部榜单 
                <span class="iconfont">&#xe60e;</span>
            </div>
        </header>
        <ul class="hotlist-ul">
             <li v-for="(item, index) of hotlist" :key="item.id">
                <a class="hotlist-item">
                    <div class="top-tip" v-if="hottip[index]">
                        <img :src="hottip[index]">
                    </div>
                    <img class='list-item-img' :src="item.imgUrl" alt="">
                    <p>{{item.name}}</p>
                    <p class="price">
                        <span>￥</span>
                        <span>{{item.price}}</span>
                         起 
                    </p> 
                </a>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "HomeHotlist",
        props: {
            hotlist: Array,
            hottip: Array
        },
        computed: {
            showTip: function() {
                for(let i = 0; i < 3; i++) {
                    this.hotList[i].showTipImage = this.hottip[i];
                }
            }
        }
    }
</script>

<style lang="stylus" scoped>
    @import '../../../assets/styles/varibles.styl'
    @import '../../../assets/styles/mixins.styl'
        
    .hotlist
        margin-top: .2rem
        background: $bgWhite
        padding: 0 .2rem
        header
            padding: 0.35rem 0
            display flex
            justify-content space-between
            align-items center
            .header-left
                display flex
                align-items center
                img 
                    width: 15px
                    height: 15px
                h3 
                    subtitle()
            .header-right
                 font-size .24rem
                 color #616161
                 span 
                    font-size .22rem
                 
        .hotlist-ul 
            overflow-x scroll   
            white-space nowrap
            padding .2rem 0
            li 
                display: inline-block
                &:not(:first-child)
                    margin-left: .1rem
                .hotlist-item 
                    display block
                    position relative
                    .top-tip
                        width: .84rem
                        heigth: .4rem
                        position absolute
                        top: -5px
                        img 
                            width 100%
                    .list-item-img
                        width 100px
                        heigth 100px
                    p
                        box-sizing border-box
                        padding: 0.1rem
                        text-align center
                        font-size .24rem
                        max-width 100px
                        ellipsis()
                        color #212121
                        span 
                            font-size .28rem
                            color #ff8300
                     
                       
        

</style>


