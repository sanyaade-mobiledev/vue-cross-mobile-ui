# Panel 图文面板


```handlebars
<template>
  <div class="demo-block padding-tb-20">
    <v-group title="切换样式">
      <v-radio title="type" v-model="type" :options="['1', '2', '3', '4', '5']"></v-radio>
    </v-group>
    <v-panel header="图文组合列表" :footer="footer" :list="list" :type="type" @on-img-error="onImgError"></v-panel>
  </div>
</template>
<script>
export default {
  methods: {
    onImgError(item, $event) {
      console.log(item, $event)
    }
  },
  data() {
    return {
      type: '1',
      list: [{
        src: 'http://somedomain.somdomain/x.jpg',
        fallbackSrc: 'http://placeholder.qiniudn.com/60x60/3cc51f/ffffff',
        title: '标题一',
        desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
        url: '/component/cell'
      }, {
        src: 'http://placeholder.qiniudn.com/60x60/3cc51f/ffffff',
        title: '标题二',
        desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
        url: {
          path: '/component/radio',
          replace: false
        },
        meta: {
          source: '来源信息',
          date: '时间',
          other: '其他信息'
        }
      }],
      footer: {
        title: '查看更多',
        url: 'http://baidu.com'
      }
    }
  }
}
</script>
```


## API

| 参数 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| header | String | | '头部文字' | 
| footer | Object | | '尾部配置，`{url: url, title: title}`' | 
| list | Array | false | '内容列表，`[{title, desc, src, fallbackSrc, meta:{source,date,other}}]`' | 
| type | String | 1 | '布局类型，可选值 ['1', '2', '3', '4', '5']' | 


### Event 
| 名字 | 参数 | 说明 |
| --- | --- | --- |
| @on-click-header |  | 点击头部时触发 |
| @on-click-item | (item) | 点击内容列表时触发 |
| @on-click-footer |  | 点击尾部时触发 |

