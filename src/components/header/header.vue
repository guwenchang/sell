<template>
  <div class="header">
      <div class="content-wrapper">
          <div class="avatar">
            <img width="64" height="64" :src="seller.avatar">
          </div>
          <div class="content">
              <div class="title">
                <span class="brand"></span>
                <span class="name">{{seller.name}}</span>
              </div>
              <div class="descriptiom">
                {{seller.description}}/{{seller.deliveryTime}} 分钟送达
              </div>
              <div v-if="seller.supports" class="support">
                <span class="icon"></span>
                <span class="text">{{seller.supports[0].description}}</span>

              </div>

          </div>
      </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: {
      seller: {
        type: Object
      }
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" rel="stylesheet/stylus">
  @import "../../common/stylus/minxin.styl"
  .header
    color: #fff
    background: #000
    .content-wrapper
      padding: 24px 12px 18px 24px
      font-size: 0
    .avatar
      vertical-align: top
      display: inline-block
      img
        border-radius: 2px
    .content
      display: inline-block
      margin-left: 16px
      .title
        margin 2px 0 8px 0
        .brand
          vertical-align: top
          display: inline-block
          width: 30px
          height: 16px
          bg-image('brand')
          background-size: 30px 18px
          background-repeat: no-repeat
        .name
          margin-left: 6px
          font-size: 16px
          line-height: 18px
          font-weight: bold
      .descriptiom
        margin-bottom: 10px
        line-height: 12px
        font-size: 12px



</style>
