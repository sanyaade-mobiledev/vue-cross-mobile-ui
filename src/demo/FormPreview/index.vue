<template>
  <div class="demo-block padding-tb-20">
    <v-form-preview header-label="付款金额" header-value="¥2400.00" :body-items="list" :footer-buttons="buttons1"></v-form-preview>
    <br>
    <v-form-preview header-label="付款金额" header-value="¥2400.00" :body-items="list" :footer-buttons="buttons2" name="demo"></v-form-preview>
    <br>
    <v-form-preview header-label="付款金额" header-value="¥2400.00" :body-items="list"></v-form-preview>
  </div>
</template>
<script>
export default {
  data() {
    return {
      list: [{
        label: '商品',
        value: '电动打蛋机'
      }, {
        label: '标题标题',
        value: '名字名字名字'
      }, {
        label: '标题标题',
        value: '很长很长的名字很长很长的名字很长很长的名字很长很长的名字很长很长的名字'
      }],
      buttons1: [{
        style: 'default',
        text: '辅助操作'
      }, {
        style: 'primary',
        text: '跳转到首页',
        link: '/'
      }],
      buttons2: [{
        style: 'primary',
        text: '点击事件',
        onButtonClick: (name) => {
          console.info(`clicking ${name}`)
        }
      }]
    }
  }
}
</script>