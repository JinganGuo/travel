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
             <li v-for="(item, index) of hotList" :key="item.id">
                <a class="hotlist-item">
                    <div class="top-tip" v-if="item.showTipImage != ''">
                        <img :src="topImg[index]">
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
        data: function(){
            return {
                topImg: [
                    "http://img1.qunarzz.com/piao/fusion/1710/ab/159673b63e6ca702.png",
                    "http://img1.qunarzz.com/piao/fusion/1710/2d/36d0c4adaebbbc02.png",
                    "http://img1.qunarzz.com/piao/fusion/1710/67/edc47ffef9e96b02.png"
                ],
                hotList: [{
                    id: '001',
                    imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_150x150_06cb3e52.jpg',
                    name: '故宫',
                    price: 20
                },{
                    id: '002',
                    imgUrl: 'http://img1.qunarzz.com/sight/p0/1708/2b/2b3b94de99c0a425a3.img.jpg_150x150_2dec3e78.jpg',
                    name: '八达岭长城',
                    price: 25
                },{
                    id: '003',
                    imgUrl: 'http://img1.qunarzz.com/sight/p0/1704/d6/d62a708bc69472f5a3.img.jpg_150x150_54ba6c62.jpg',
                    name: '十渡聚龙湾玻璃栈道',
                    price: 35
                },{
                    id: '004',
                    imgUrl: 'http://img1.qunarzz.com/sight/p0/1501/40/40b2b6c951b28fdd.water.jpg_150x150_8a63d940.jpg',
                    name: '水立方',
                    price: 14
                },{
                    id: '005',
                    imgUrl: 'http://img1.qunarzz.com/sight/p0/201405/30/63494597d8a8346abd77cc9e1cd2ee79.jpg_150x150_7037ca72.jpg',
                    name: '定陵',
                    price: 50
                },{
                    id: '006',
                    imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/a5/4003f9dd7bebf61eccbf64046e26d487.water.jpg_150x150_27594131.jpg',
                    name: '北京欢乐谷',
                    price: 49
                },{
                    id: '007',
                    imgUrl: 'http://img1.qunarzz.com/sight/p0/1505/d2/d274c92de14c93da.water.jpg_150x150_2747e538.jpg',
                    name: '颐和园',
                    price: 48
                },{
                    id: '008',
                    imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/c0/0ddded36771ed10c9e03eb64794610cb.water.jpg_150x150_69bf7d53.jpg',
                    name: '仙栖洞',
                    price: 38
                },{
                    id: '009',
                    imgUrl: 'http://img1.qunarzz.com/sight/p0/201306/13/bdf22f69fab0ee4ec8d65eac.jpg_150x150_35b4b15f.jpg',
                    name: '八达岭长城缆车',
                    price: 155
                },{
                    id: '010',
                    imgUrl: 'http://img1.qunarzz.com/sight/p0/1801/bf/bfd58fbb6aec7a15a3.img.jpg_150x150_7040715c.jpg',
                    name: '故宫礼物',
                    price: 9
                }]
            }
        },
        computed: {
            showTip: function() {
                for(let i = 0; i < 3; i++) {
                    this.hotList[i].showTipImage = this.topImg[i];
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


