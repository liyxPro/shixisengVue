<template>
  <div>
    <!-- :footer="footer"  -->
    <!-- <panel :list="list" :type="type" @on-img-error="onImgError"></panel> -->
    <ul class="panelBox" :list="list">
      <li class="jobBox"  v-for="items in list">
      
        <div class="companyImg">
          <img :src="require('../assets/static/'+items.cimg)" alt="">
        </div>
        <div class="companyCont">
          <span>{{items.jtitle}}</span>
          <p class="jobType">{{items.cname}}</p>
          <p>
            <span class="jobPosition">{{items.ccity}}</span>
            <span class="jobLongTime">{{items.jtime}}个月</span>
          </p>
        </div>
        <div class="rightCont">
          <p class="jobTime">{{items.jpubTime}}</p>
          <p class="jobSalary">￥ {{items.jminsalary}}-{{items.jmaxsalary}}/天</p>
        </div>
      </li>
      
    </ul>
  </div>
</template>
<script>
import { Panel } from 'vux'
import $ from 'jquery'
export default {
  name: 'internsList',
  components: {
    Panel
  },
  methods: {
    onImgError (item, $event) {
      console.log(item, $event)
    }
  },
  data () {
    return {
      type: '1',
      list: [],
      footer: {
        title: 'more',
        url: 'http://vux.li'
      }
    }
  },
  mounted () {
    this.$nextTick(() => {
      var that = this
      $.ajax({
        type: 'get',
        url: 'http://39.106.24.44:80/shixiseng/data/internList.php',
        dataType: 'jsonp',
        success: function (data) {
          that.list = data
          console.log(data)
          function format (times) {
            function formatTimes (t) {
              return `${t < 10 ? 0 : ''}${t}`
            }
            var time = `${formatTimes(times.getMonth() + 1)}-${formatTimes(times.getDay())}-${formatTimes(times.getHours())}:${formatTimes(times.getMinutes())}`
            console.log(time)
            return time
          }
          for (let item of data) {
            var times = new Date(item.jpubTime)
            var formatTime = format(times)
            item.jpubTime = formatTime
          }
        }
      })
    })
  }
}
</script>
<style>
  .jobBox{
    display: flex;
    justify-content: space-between;
    flex-wrap:nowrap;
    align-items: stretch;
    padding-bottom: 20px;
    margin-top: 20px;
    border-bottom: 1px solid #F7F9FA;
  }
  .companyImg img{
    width: 60px;
    height: 60px;
  }
  .companyCont{
    flex-grow: 2;
    margin-left: 10px;
    color: #5A647A;
  }
  .jobBox p{
    font-size: x-small;
    color: #BDC9DA;
  }
  p.jobSalary{
    color: #F96969;
    font-weight: bold;
  }
  .rightCont{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-end;
  }
  .panelBox{
    margin-top: 10px;
    background-color: #ffffff;
    padding: 10px 15px 20px;
  }
  p.jobTime{
    color:#D4DDEF
  }
</style>

