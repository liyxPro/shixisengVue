<template>
  <div class="containerBox">
   <HeaderSxs></HeaderSxs> 
   <!-- <input type="text" v-model="msg">
   <div v-on:click="changeData">请点击我更换内容

   </div> -->
   <SearchTips></SearchTips>
   <InternsList></InternsList>
   <div class="moreInterns">
     前往职位列表，查看更多职位
   </div>
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
<style>
  .containerBox{
    padding-bottom: 50px;
  }
  .moreInterns{
    text-align: center;
    height: 30px;
    background-color: #ffffff;
    margin-top: 15px;
    padding: 10px 0;
    color: #54B2FF;
  }
</style>
