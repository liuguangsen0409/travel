<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <router-link tag="li" :to="'/detail/' + item.id" class="item border-bottom" v-for="item of list" :key="item.id">
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
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
.item
  display: flex
  height: 2rem
  overflow: hidden
  .item-img
    width: 1.7rem
    height: 1.7rem
    padding: .15rem .2rem
  .item-info
    flex: 1
    min-width: 0
    padding: .2rem
    .item-title
      line-height: .54rem
      font-size: .32rem
      ellipsis()
    .item-desc
      line-height: .4rem
      font-size: .28rem
      color: #cccccc
      ellipsis()
    .item-button
      background: #ff9300
      padding: 0 .1rem
      margin-top: .16rem
      color: #ffffff
      line-height: .44rem
      border-radius: .06rem
</style>
