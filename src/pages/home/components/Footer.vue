<template>
    <div class="footer">
        <ul class="links">
            <li>
                机票
            </li>
            <li>
                酒店
            </li>
            <li>
                公寓
            </li>
            <li>
                |
            </li>
            <li>
                更多
            </li>
        </ul>
        <ul class="self-links">
            <li><a href="#">登录</a></li>
            <li><a href="#">我的订单</a></li>
            <li><a href="#">最近浏览</a></li>
            <li><a href="#">关于我们</a></li>
        </ul>
        <div class="rights">
            <a href="#">触屏版</a>
            <a href="#">电脑版</a>
            <p>www.guojingan.cn &copy; 2018.6 意见反馈</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'HomeFooter'
    }
</script>

<style lang="stylus" scoped>
    .footer
        
        .links
            padding .2rem
            display flex
            justify-content center
            li 
                padding: 0.1rem .4rem
                color #9e9e9e
                font-size 12px
                text-decoration underline
        .self-links 
            display flex
            padding: .3rem 
            border-bottom 1px solid gray
            li  
                padding  0 .1rem   
                font-size 14px
        .rights
            text-align center
            padding .2rem
            a 
                font-size 14px
                display inline-block
                margin-right .3rem
                &:first-child
                    color black
            p 
                color #9e9e9e
                font-size 14px
                padding .2rem 0 .1rem 0
</style>

