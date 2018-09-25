<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOptions">
        <swiper-slide v-for="(item, index) in imgs" :key="index">
          <img class="gallary-img" :src="item" />
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        // swiper监听父级或自己变化时自我刷新
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    /**
     * 点击gallary组件 触发父组件close方法
     */
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
.container >>> .swiper-container
  overflow: inherit
.container
  z-index: 99
  position: fixed
  top: 0
  right: 0
  bottom: 0
  left: 0
  background: #000
  display: flex
  flex-direction: column
  justify-content: center
  .wrapper
    width: 100%
    height: 0
    padding-bottom: 70%
    .gallary-img
      width: 100%
    .swiper-pagination
      color: #fff
      bottom: -1rem
</style>
