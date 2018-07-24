<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: 3000,
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1807/22/382624cbe97b0502.jpg_750x200_36a074d6.jpg'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1807/a1/41a802abfc4f0202.jpg_750x200_9f0cf69c.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background: #ffffff
.wrapper
  width: 100%
  height: 0
  overflow: hidden
  padding-bottom: 26.67%
  .swiper-img
    width: 100%
</style>
