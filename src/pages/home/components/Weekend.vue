<template>
  <div>
    <div class="title">周末去哪</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommandList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommandList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1606/a2/c10424cf4acf79.jpg_r_640x214_d83730b5.jpg',
        title: '黄花沟',
        desc: '详情详情详情详情详情详情详情详情详情详情详情详情详情详情详情详情'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1606/a2/c10424cf4acf79.jpg_r_640x214_d83730b5.jpg',
        title: '黄花沟',
        desc: '详情详情详情详情详情详情详情详情详情详情详情详情详情详情详情详情'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1606/a2/c10424cf4acf79.jpg_r_640x214_d83730b5.jpg',
        title: '黄花沟',
        desc: '详情详情详情详情详情详情详情详情详情详情详情详情详情详情详情详情'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.title
  line-height: .8rem
  background: #eeeeee
  text-indent: .2rem
  margin-top: .2rem
.item-img-wrapper
  height: 0
  overflow: hidden
  padding-bottom: 33.9%
  .item-img
    width: 100%
.item-info
  padding: .2rem
  .item-title
    line-height: .54rem
    font-size: .32rem
    ellipsis()
  .item-desc
    line-height: .4rem
    color: #cccccc
    ellipsis()
</style>
