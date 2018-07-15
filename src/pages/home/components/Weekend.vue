<template>
    <div class="weekend">
        <h3>周末去哪儿</h3>
        <ul class="weekend-list">
            <li v-for="item of weekendlist" :key="item.id">
                <a href="#">
                    <img :src="item.imgUrl" alt="">
                    <p class="title">{{item.title}}</p>
                    <p class="subtitle">{{item.subtitle}}</p>
                </a>
            </li>
        </ul>
        <div class="introduce">
            <span class="iconfont">&#xe71a;</span>
            <strong>  
                票面价
            </strong>
            是指通过景区指定窗口售卖的纸质门票上标注的价格
        </div>
    </div>
</template>

<script>
    export default {
        name: "HomeWeekend",
       props: {
           weekendlist: Array
       }
    }
</script>

<style lang="stylus" scoped>
    @import '../../../assets/styles/varibles.styl'
    @import '../../../assets/styles/mixins.styl'

    .weekend
        h3 
            padding: .3rem   
            ellipsis()
        .weekend-list
            background $bgWhite
            li 
                padding-bottom .2rem
                a 
                    img  
                        width 100%
                    p 
                        padding .2rem .2rem .1rem .2rem
                        ellipsis()
                    .title
                        color: #212121
                        font-size .28rem
                    .subtitle
                        color: #616161
                        font-size .24rem
        .introduce 
            margin-top .1rem
            background $bgWhite
            font-size .24rem
            padding .1rem .2rem
            color #616161
            span 
                font-size 12px
            strong 
                font-weight bold
</style>

