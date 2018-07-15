<template>
    <div class="weekend">
        <h3>周末去哪儿</h3>
        <ul class="weekend-list">
            <li v-for="item of weekendList" :key="item.id">
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
        data: function(){
            return {
                weekendList: [
                    {
                        id: '001',
                        imgUrl: 'http://img1.qunarzz.com/sight/source/1606/85/c6b6bad1b977e.jpg_r_640x214_5c638941.jpg',
                        title: '漂流勇进，烧烤露营',
                        subtitle: '轻松水上漂，任我乐逍遥'
                    },
                     {
                        id: '002',
                        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/53/02091f1ee43d0a.jpg_r_640x214_2e3256b1.jpg',
                        title: '北京清凉避暑胜地',
                        subtitle: '到大自然中享受“天然空调”的清凉'
                    },
                    {
                        id: '003',
                        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
                        title: '北京必游TOP10',
                        subtitle: '来北京必去的景点非这些地方莫属'
                    },
                     {
                        id: '004',
                        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
                        title: '寻找北京的皇城范儿',
                        subtitle: '数百年的宫廷庙宇，至今依旧威严霸气'
                    },
                      {
                        id: '005',
                        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/ce/bc89bc2f0e33ea.jpg_r_640x214_3e408453.jpg',
                        title: '学生最爱的博物馆',
                        subtitle: '周末干嘛？北京很多博物馆已经免费开放啦'
                    }
                ]
            }
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

