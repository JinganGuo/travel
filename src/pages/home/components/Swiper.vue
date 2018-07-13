<template>
  <div class="img-container">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item in imgList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" :alt="item.imgAlt" >
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
  export default {
    name: 'HomeSwiper',
    data: function () {
      return {
        swiperOption: {
            pagination: '.swiper-pagination',
            loop: true,
            autoplay: 3000
        },
        imgList: [
            {
                id: "001",
                imgUrl: "http://img1.qunarzz.com/piao/fusion/1807/ec/278a34afb59a0d02.jpg_750x200_3292a705.jpg",
                imgAlt: "远去的恐龙"
            },
            {
                id: "002",
                imgUrl: "http://img1.qunarzz.com/piao/fusion/1806/f5/ea83238744f31102.jpg_750x200_73b8477c.jpg",
                imgAlt: "卡塔尔的讲述"
            },
            {
                id: "003",
                imgUrl: "http://img1.qunarzz.com/piao/fusion/1807/a1/41a802abfc4f0202.jpg_750x200_9f0cf69c.jpg",
                imgAlt: "上海迪士尼乐园"
            },
            {
                id: "004",
                imgUrl: "http://img1.qunarzz.com/piao/fusion/1806/3c/c72a1ccd4d7b2202.jpg_750x200_b88bbab4.jpg",
                imgAlt: "奇妙暑假在长隆"
            }
        ]
      }
    }
  }
</script>

<style lang="stylus" scoped>
.img-container >>> .swiper-pagination-bullet-active
    background-color: #ffffff
.img-container
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 26.66%    
    background: #cccccc 
    .swiper-img 
        width: 100%
</style>