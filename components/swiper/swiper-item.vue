<template>
  <div class="vcu-swiper-item">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'v-swiper-item',
  mounted() {
    this.$nextTick(() => {
      this.$parent.rerender()
    })
  },
  beforeDestroy() {
    const $parent = this.$parent
    this.$nextTick(() => {
      $parent.rerender()
    })
  }
}
</script>
