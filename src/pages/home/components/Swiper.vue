<template>
  <div class="img-container">
    <swiper :options="swiperOption" v-if="list.length">
      <!-- slides -->
      <swiper-slide v-for="item in list" :key="item.id">
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
    props: {
      list: Array
    },
    data: function () {
      return {
        swiperOption: {
            pagination: '.swiper-pagination',
            loop: true,
            autoplay: 3000
        }
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