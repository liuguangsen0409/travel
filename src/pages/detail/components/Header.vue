<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
      <div class="iconfont header-abs-back">&#xe624;</div>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <router-link to='/'>
        <div class="iconfont header-fixed-back">&#xe624;</div>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    /**
     * 滚动屏幕监听头部显示隐藏
     */
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    /**
     * 监听滚动事件 触发handleScroll方法
     */
    window.addEventListener('scroll', this.handleScroll)
  },
  // TODO 页面被隐藏触发
  deactivated () {
    /**
     * 页面关闭前 解绑全局滚动触发handleScroll
     */
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header-abs
  position: absolute
  left: .2rem
  top: .2rem
  width: .8rem
  height: .8rem
  border-radius: .4rem
  text-align: center
  line-height: .8rem
  background: rgba(0, 0, 0, .8)
  .header-abs-back
    color: #fff
    font-size: .4rem
.header-fixed
  font-size: .32rem
  height: $headerHeight
  line-height: $headerHeight
  text-align: center
  color: #ffffff
  background: $bgColor
  position: fixed
  top: 0
  left: 0
  right: 0
  .header-fixed-back
    width: .64rem
    text-align: center
    font-size: .4rem
    position: absolute
    top: 0
    left: 0
    color: #ffffff
</style>
