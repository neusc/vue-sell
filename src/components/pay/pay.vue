<template>
  <transition name="move">
    <div v-show="showFlag" class="pay-wrapper" ref="pay">
      总共支付{{totalPrice}}元！
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
    transform: translate3d(0,0,0)
    &.move-enter-active, &.move-leave-active
      transition: all 0.2s liner
    &.move-enter, &.move-leave-enter
      transform: translate3d(100%,0,0)
</style>
