<template>
  <transition name="move">
    <div v-show="showFlag" class="pay-wrapper" ref="pay">
      <div class="pay-way">
        <div class="pay-title">选择付款方式</div>
        <label for="ali-check-btn" class="alipay-wrapper pay-option" data-checked="true">
          <img class="alipay-icon" src="http://p0.jmstatic.com/mobile/touch/Image/duobao/zhenl3/alipay-icon.png"/>
          <div class="alipay-des-wrapper">
            <div class="alipay-des-top">支付宝</div>
            <div class="alipay-des-bottom">客户端支付最便捷！可银行卡支付</div>
          </div>
          <div class="check-btn-wrapper">
            <input type="radio" id="ali-check-btn" class="check-btn" name="check-btn" value="alipay" checked/>
            <label class="check-btn-label" for="ali-check-btn"></label>
          </div>
        </label>
        <label for="wx-check-btn" class="wxpay-wrapper pay-option">
          <img class="wxpay-icon" src="http://p0.jmstatic.com/mobile/touch/Image/duobao/zhenl3/wxpay-icon.png"/>
          <div class="wxpay-des-wrapper">
            <div class="wxpay-des-top">微信支付</div>
            <div class="wxpay-des-bottom">亿万用户的选择，更快更安全</div>
          </div>
          <div class="check-btn-wrapper">
            <input type="radio" id="wx-check-btn" class="check-btn" name="check-btn" value="wxpay"/>
            <label class="check-btn-label" for="wx-check-btn"></label>
          </div>
        </label>
      </div>
    </div>
  </transition>
</template>

<script type="text/ecmascript-6">
  export default {
    props: {
      totalPrice: {
        type: Number
      }
    },
    data() {
      return {
        showFlag: false
      };
    },
    methods: {
      show() {
        this.showFlag = true;
      }
    }
  };
</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import "../../common/stylus/mixin.styl"

  .pay-wrapper
    position: fixed
    left: 0
    top: 0
    z-index: 60
    width: 100%
    height: 100%
    background: #fff
    transform: translate3d(0, 0, 0)
    &.move-enter-active, &.move-leave-active
      transition: all 0.2s liner
    &.move-enter, &.move-leave-enter
      transform: translate3d(100%, 0, 0)
</style>
