<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
    <div class="tab">
      <div class="tab-item">
        <router-link to='/goods'>商品</router-link>
      </div>
      <div class="tab-item">
        <router-link to='/ratings'>评价</router-link>

      </div>
      <div class="tab-item">
        <router-link to='/seller'>商家</router-link>

      </div>
    </div>
    <router-view></router-view>


  </div>

</template>

<script type="text/ecmascript-6">
  import header from './components/header/header.vue'
  import staticVal from './const'
  import router from './router'
  export default{
    data () {
      return {
        seller: {}
      }
    },
    components: {
      'v-header': header
    },
    created () {
      this.$http.get('/api/seller').then(response => {
        response = response.body
        if (response.status === staticVal.request_success) {
          this.seller = response.data
          console.log(this.seller)
        }
      }, response => {
        // error callback
        console.log('请求失败')
      })
    }
  }
  router.push('/goods')

</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import "common/stylus/minxin.styl"


  #app
    .tab
      display: flex
      width: 100%
      height: 40px
      line-height: 40px
      border-1px(rgba(7, 17, 27, 0.1))
      .tab-item
        flex: 1
        text-align: center
        &>a
          display: block
          font-size: 14px
          color: rgb(77,85,93)
          &.active
            color: rgb(240, 20, 20)

</style>
