<template>
    <div class="icon-container">
        <swiper :options="swiperOption">
             <swiper-slide class="icon-page" v-for="(page, index) of pages" :key="index">
                <div class="icon-item" v-for="item of page" :key="item.iconId">
                    <img class="icon-img" :src="item.iconUrl" :alt="item.iconIntr">
                    <p>{{item.iconIntr}}</p>
                </div>
             </swiper-slide>
             <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
    export default {
        name: 'HomeIcons',
        data: function(){
            return {
                swiperOption: {
                    pagination: '.swiper-pagination',
                    loop: false
                },
                iconList: [{
                        iconId: '001',
                        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                        iconIntr: '景点门票'
                    }, {
                        iconId: '002',
                        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
                        iconIntr: '必游榜单'
                    }, {
                        iconId: '003',
                        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
                        iconIntr: '夏日玩水'
                    }, {
                        iconId: '004',
                        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
                        iconIntr: '主题乐园'
                    }, {
                        iconId: '005',
                        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
                        iconIntr: '动植物园'
                    }, {
                        iconId: '006',
                        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
                        iconIntr: '故宫'
                    }, {
                        iconId: '007',
                        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
                        iconIntr: '一日游'
                    }, {
                        iconId: '008',
                        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/54/35899492b1302802.png',
                        iconIntr: '公园'
                    }, {
                        iconId: '009',
                        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
                        iconIntr: '游乐场'
                    }, {
                        iconId: '010',
                        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
                        iconIntr: '全部玩乐'
                    }
                ]
            }
        },
        computed: {
            pages () {
                const pages = []
                this.iconList.forEach((item, index) => {
                    const page = Math.floor(index / 8)
                    if(!pages[page]) {
                        pages[page] = []
                    }

                    pages[page].push(item)
                })
                return pages
            }
        }
    }
</script>

<style lang="stylus" scoped>
    @import '../../../assets/styles/varibles.styl';
     @import '../../../assets/styles/mixins.styl';

    .icon-container >>> .swiper-pagination
        position: static
        margin-top: .2rem
    .icon-container >>> .swiper-pagination-bullet-active
        background: rgba(0,175,190,.8) 
    .icon-container >>> .swiper-pagination-bullet
        height: 6px
        width: 6px

    .icon-container
        .icon-page
            width: 100%
            box-sizing: border-box
            padding-top: .2rem
            display: flex
            flex-wrap: wrap
            .icon-item
                width: 25%
                text-align: center
                box-sizing: border-box
                padding-top: .15rem
                .icon-img
                    width: 55px
                    height: 55px
                p
                    padding-top: .1rem
                    ellipsis()
</style>

