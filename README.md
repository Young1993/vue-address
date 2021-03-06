# vue-address

> 多级联动地址选择器


## install

>npm install vue-address-tky --save

## import

```js
import vueAddress from 'vue-address-tky'
import "vue-select/lib/vue-address.min.css";
...

Vue.component('vue-address-tky', vueAddress)
```

## usage

```html
<template>
  <div id="app">
    <img src="./assets/logo.png">
    <x-address @change="selectAddress"  @close="closeMask"></x-address>
    <div id="address" v-text="selectedAddress"></div>
  </div>
</template>

<script>
import xAddress from 'vue-address-tky'

export default {
  name: 'app',
  components: {
    xAddress
  },
  data: () => {
    return {
        selectedAddress: ''
    }
  },
  methods: {
    selectAddress(province, city, detail) {
        this.selectedAddress = `${province}, ${city}, ${detail}`
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```

## 特别感谢

+   [Administrative-divisions-of-China](https://github.com/modood/Administrative-divisions-of-China) 中国行政区划数据：省份、城市、区县、乡镇，省市区镇三级四级联动。
+   [vue-address](https://github.com/WebCodeFarmer/vue-address) 多级联动地址选择器
