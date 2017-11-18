<template>
  <ul class="searchBox">
     <li  v-for="item in bar_icon"> 
        <img  :src='item.img' alt="">
        <br>
        <!-- {{msg}} -->
        <span>{{ item.title }}</span>
     </li>
  </ul>
  
</template>
<script>
const barIcon = [{
  url: 'javascript:',
  img: './static/bar-icon1.png',
  title: '短期实习'
}, {
  url: 'javascript:',
  img: './static/bar-icon2.png',
  title: '一周两天'
}, {
  url: 'javascript:',
  img: './static/bar-icon3.png',
  title: '转正机会'
}, {
  url: 'javascript:',
  img: './static/bar-icon4.png',
  title: '日薪200'
}
]
export default {
  name: 'searchTips',
  data () {
    return {
      bar_icon: barIcon
    }
  },
  props: {
    msg: {
      type: [String, Object, Array],
      default: ' waiting world '
    }
  },
  updated () {
    console.log('updated:')
    console.log(this.msg)
  }
}
</script>
<style>
  .searchBox{
    margin: 0 auto;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    padding:10px 20px;
    background-color: #ffffff;
  }
  .searchBox li{
    float: left;
    list-style: none;
    text-align: center;
    margin: 0 5px;
    cursor: pointer;
  }
  .searchBox img{
    display: inline-block;
    width: 60px;
    height: 60px;
  }
</style>
