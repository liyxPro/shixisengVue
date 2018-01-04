<template>
  <header>
    <div class="vue-banner">
      <span class="searchButton">搜索</span>
      <swiper :list="demo01_list" v-model="demo01_index" :aspect-ratio="300/800" @on-index-change="demo01_onIndexChange"></swiper>
      <!--<p>current index: {{demo01_index}}</p>
      <x-button @click.native="demo01_index = 0">go to 0</x-button>
      <x-button @click.native="demo01_index = 1">go to 1</x-button>
      <x-button @click.native="demo01_index = 2">go to 2</x-button>  -->
    </div>
    <div class="vue-search"></div>
  </header>
</template>

<script>
import { Swiper, GroupTitle, SwiperItem, XButton, Divider } from 'vux'
const baseList = [{
  url: 'javascript:',
  img: 'https://static.vux.li/demo/1.jpg'
}, {
  url: 'javascript:',
  img: 'https://static.vux.li/demo/2.jpg'
}, {
  url: 'javascript:',
  img: 'https://static.vux.li/demo/3.jpg',
  fallbackImg: 'https://static.vux.li/demo/3.jpg'
}]

export default {
  name: 'header',
  components: {
    Swiper,
    SwiperItem,
    GroupTitle,
    XButton,
    Divider
  },
  data () {
    return {
      demo01_list: baseList,
      demo01_index: 0
    }
  },
  methods: {
    demo01_onIndexChange (index) {
      this.demo01_index = index
    }
  }
}
</script>
<style>
 .searchButton{
   position: absolute;
   background-color:rgba(155,155,155,0.5);
   width: 50px;
   height: 30px;
   border-radius: 10px;
   z-index: 999;
   text-align: center;
   right: 20px;
   top: 20px;
   color: #fff;
 }
header{
   position: relative
}
</style>
