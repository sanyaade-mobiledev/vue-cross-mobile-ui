<template>
  <div class="demo-wrap" :style="{ top: positionTop + 'px' }">
    <div class="mobile-top" />
    <iframe id="iframe-demo" :src="demourl" frameborder="0" />
  </div>
</template>

<script>
export default {
  name: 'vcu-demo',

  props: {
    demourl: {
      type: String,
      default: 'http://vcumobile-demo.getvcu.com/#/home'
    },
    stickyTop: {
      type: Number,
      default: 84
    }
  },

  data() {
    return {
      positionTop: this.stickyTop
    }
  },


  mounted() {
    // 右侧 DEMO 区实在 sticky 效果
    document.addEventListener('scroll', () => {
      const scrollDistance = Math.abs(document.body.getBoundingClientRect().top)
      if (scrollDistance >= this.stickyTop - 80) {
        this.positionTop = scrollDistance + 80
      } else {
        this.positionTop = this.stickyTop
      }
    })
  }
}
</script>

<style scoped lang="less">
.demo-wrap {
  display: block;
  overflow: hidden;
  width: 375px;
  min-width: 375px;
  z-index: 50;
  border-radius: 6px;
  background: #f2f2f2;
  box-sizing: border-box;
  right: 15px;
  position: absolute;
  box-shadow: #999 -3px 3px 20px;

  .mobile-top {
    display: block;
    overflow: hidden;
    width: 100%;
    height: 42px;
    background: url(./assets/mobile_top.jpg) left top no-repeat;
    background-size: contain;
  }

  iframe {
    width: 100%;
    height: 555px;
  }
}
</style>
