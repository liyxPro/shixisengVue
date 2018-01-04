<template>
  <div class="footer">
    <tabbar class="footerTab" v-model="index" :click="tabClick()">
      <tabbar-item>
        <img slot="icon" src="../assets/demo/index.png">
        <span slot="label">首页</span>
      </tabbar-item>
      <tabbar-item>
        <img slot="icon" src="../assets/demo/job.png">
        <span slot="label">职位</span>
      </tabbar-item>
      <tabbar-item >
        <img slot="icon" src="../assets/demo/mine.png">
        <span slot="label">我的</span>
      </tabbar-item>
    </tabbar>
  </div>
</template>
<script>
import { Tabbar, TabbarItem } from 'vux'
export default {
  name: 'footer',
  components: {
    Tabbar,
    TabbarItem
  },
  data () {
    return {
      index: 0
    }
  },
  methods: {
    tabClick () {
      console.log(this.index)
    }
  }
}
</script>
<style>
  /* .footer div{
      position: fixed;
  } */
  .footer{
      padding: 10px 0;
  }
  .footer .footerTab span{
     color: #5a8efb;
  }
</style>
