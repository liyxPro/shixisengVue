<template>
  <div>
   <HeaderSxs></HeaderSxs> 
   <!-- <input type="text" v-model="msg">
   <div v-on:click="changeData">请点击我更换内容

   </div> -->
   <SearchTips></SearchTips>
   <InternsList></InternsList>
  </div>
  
</template>

<script>
import HeaderSxs from './header'
import SearchTips from './search_tips'
import InternsList from './internsList'
export default {
  components: {
    HeaderSxs,
    SearchTips,
    InternsList
  },
  data () {
    return {
      msg: [],
      msg1: 'hello my world',
      obj: {
        'name': 'xiaoming'
      }
    }
  },
  creatd () {
    this.msg = this.msg1
  },
  methods: {
    changeData: function () {
      this.msg = this.obj
    }
  }
}
</script>
