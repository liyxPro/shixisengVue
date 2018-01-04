<template>
  <div id="app" style="height:100%;">
   
    <view-box ref="viewBox">
      <router-view></router-view>  
    </view-box>
   
  </div>
</template>

<script>
import { ViewBox } from 'vux'
export default {
  name: 'app',
  components: {
    ViewBox
  }
}
</script>

<style lang="less">
@import '~vux/src/styles/reset.less';

html, body {
    height: 100%;
    width: 100%;
    overflow-x: hidden;
}
body {
  background-color: #fbf9fe;
}
</style>
