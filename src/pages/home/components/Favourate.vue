<template>
    <div class="favourate">
        <header>
            <img src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="">
             <h3>猜你喜欢</h3>
        </header>
        <ul>
            <li v-for="item of favourateList" :key="item.id">
                <a href="#" class="favourate-item">
                    <div class="left-img">
                        <div class="img-tip">
                            {{item.tip}}
                        </div>
                        <img :src="item.imgUrl" alt="">
                    </div>
                    <div class="right-info">
                        <h4>{{item.title}}</h4>
                        <p class="comment">
                            <span class="stars"></span>
                            <span>{{item.comment}}</span>条评论
                        </p>
                        <p class="price">
                            <span>
                            <em>{{item.price}}</em>
                            起</span>  
                            <span class="place">{{item.place}}</span>
                        </p>
                    </div>
                </a>
            </li>
        </ul>
        <a href="#" class="view-all">
            查看所有产品
        </a>
    </div>
</template>

<script>
    export default {
        name: "HomeFavourate",
        data: function() {
            return {
                favourateList: [
                    {
                        id: '001',
                        imgUrl: 'http://img1.qunarzz.com/sight/p0/1609/7a/7ae8ee7831836095a3.water.jpg_200x200_36727f69.jpg',
                        title: '金海湖风景区',
                        tip: '明日可定',
                        comment: 5200,
                        price: 18.8,
                        place: '平谷区'
                    },
                    {
                        id: '002',
                        imgUrl: 'http://img1.qunarzz.com/sight/p0/1803/12/126471e0966aca5ba3.img.jpg_200x200_f1286016.jpg',
                        title: '北京国际鲜花港',
                        tip: '明日可定',
                        comment: 1916,
                        price: 24.9,
                        place: '顺义区'
                    },
                      {
                        id: '003',
                        imgUrl: 'http://img1.qunarzz.com/sight/p0/1501/40/40b2b6c951b28fdd.water.jpg_200x200_fdc48968.jpg',
                        title: '水立方',
                        tip: '明日可定',
                        comment: 3660,
                        price: 14,
                        place: '奥林匹克国家公园'
                    },
                    {
                        id: '004',
                        imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/a5/4003f9dd7bebf61eccbf64046e26d487.water.jpg_200x200_7690e4cd.jpg',
                        title: '北京欢乐谷',
                        tip: '明日可定',
                        comment: 54635,
                        price: 49,
                        place: '朝阳区'
                    },
                      {
                        id: '005',
                        imgUrl: 'http://img1.qunarzz.com/sight/p0/1501/c2/c212a154649088c1.water.jpg_200x200_69d1df69.jpg',
                        title: '水立方嬉水乐园',
                        tip: '明日可定',
                        comment: 2603,
                        price: 111,
                        place: '丰台区'
                    },
                    {
                        id: '006',
                        imgUrl: 'http://img1.qunarzz.com/sight/p0/201405/23/0265195fc4b7913a758674357c3cc8f6.jpg_200x200_b58ea00b.jpg',
                        title: '北京欢乐水魔方',
                        tip: '明日可定',
                        comment: 1546,
                        price: 241,
                        place: '水立方'
                    }   
                ]
            }
        }
      
    }
</script>

<style lang="stylus" scoped>
    @import '../../../assets/styles/varibles.styl'
    @import '../../../assets/styles/mixins.styl'

    .favourate
        margin-top: .2rem
        background $bgWhite
        padding: 0 .2rem
        header 
            padding .35rem 0
            display flex
            img 
                width: 15px
                height: 15px
            h3 
                subtitle()
        ul 
            li 
                margin: .2rem 0
                 
                .favourate-item
                    display block
                    display flex
                    .left-img
                        width 100px
                        height 100px
                        position relative
                        .img-tip
                            width 1.02rem
                            height .38rem 
                            position absolute
                            background-image:url(https://img1.qunarzz.com/piao/fusion/1802/52/b9080e45b69b4f02.png)
                            font-size .2rem
                            color #ffffff
                            line-height .38rem
                            text-indent .07rem
                            border-bottom-right-radius .25rem
                        img 
                            height 100%
                    .right-info
                        padding: 0 .3rem
                        width 100%
                        min-width 0
                        h4
                            margin-top .36rem
                            font-size .32rem
                            color #212121
                            ellipsis()
                        .comment
                            margin-top .24rem
                            color: #616161
                            font-size .24rem
                        .price 
                            margin-top .32rem
                            display flex
                            justify-content space-between
                            align-items center
                            em 
                                font-size .4rem
                                color #ff8300
                                &:before
                                    content "￥"
                                    font-size .24rem
                            span 
                                font-size: .24rem    
                                color #616161
                                display inline-block
                                height .24rem
                                line-height .24rem
                            .place 
                                ellipsis()
                                max-width 80px
        .view-all 
            display: block
            padding: .3rem
            text-align center
            font-size .28rem
            border-top: 1px solid $bgGray
</style>
