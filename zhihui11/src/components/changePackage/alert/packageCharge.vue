<template>
  <div class="demo incomingHistory">            <!-- 套餐外资费 -->
    <div class="popover-main">
      <span class="titleface lh18">套餐外资费</span>
      <span class="typeface lh18 top5">1、超出套餐部分采用<span class="blue">流量自动升档</span>方式计费</span>
      <span class="typeface lh18">2、国内语音：<span class="blue">中国大陆</span>地区0.15/分钟，单次通话时长不足1分钟按1分钟计算</span>
      <span class="typeface lh18">3、国内短/彩信：中国大陆地区0.1元/条</span>
    </div>
  </div>
</template>

<style scoped>
  .demo{
    width: 300px;
    height:120px;
    background: #F7F7F7;
    margin-left: -20px;
    margin-top: -220px;
    border-radius: 5px;
    border: 1px solid #D9D9D9;
    box-shadow: 0 0 10px rgba(0,0,0,0.2);
    overflow: hidden;
    color: #333333;

    display:flex;
    flex-direction:row;
  }
  .popover-head i{          /*头关闭按钮*/
    float: right;
    color: #A1C1E2;
    font-size: 12px;
    margin-top: 13px;
    margin-right: 12px;
    cursor: pointer;
  }

  .popover-main{
    flex:1;

    padding: 15px 15px;
    /*width: calc(100% - 30px);*/
    /*background:#eb2d2d;*/

    display: flex;
    flex-direction:column;
  }

  .block-msg{
    background:#eee;
  }


  /*---------↓*/

  .option{
    background:#00ff00;
    width:100%;
    float:left;
  }

  .titleface{
    font-size:14px;
    font-family: Helvetica Neue,"微软雅黑","黑体";
    color:#333;
  }
  .blueface{
    font-size:12px;
    font-family: Helvetica Neue,"微软雅黑","黑体";
    color:#1476CC;
  }
  .typeface{
    font-size:12px;
    font-family: Helvetica Neue,"微软雅黑","黑体";
    color:#333;
  }
  .lh18{line-height:18px;}
  .top5{margin-top:5px;}

  .blue{color:#1476CC;}

  /*---------↑*/


  .table-head .head-item span{
    margin-left: 10px;
    color: #333333;
    font-size: 12px;
  }


</style>
<script>
  import { mapActions } from 'vuex'
  import { mapGetters } from 'vuex'
  export default {
    data() {
      return {

        result_one:'',
        result_two:'',

      };
    },
    computed:{
      ...mapGetters([
        ''
      ])
    },
    methods: {
      close: function () {
        alert(0)
      },
      ...mapActions([
        'popoverAlert'
      ])
    }
  };
</script>
