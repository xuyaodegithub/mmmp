<template>
  <div class="demo incomingHistory">
    <div class="popover-head">
      <span class="title">详情</span>
      <i v-on:click="popoverAlert()" class="el-icon-close"></i>     <!-- 关闭按钮 -->
    </div>
    <div class="popover-main">
      <div class="item-list-head">
          <div class="item">支出</div>
          <div class="item">账本类型</div>
      </div>
      <div class="item-list" v-for="item in balanceChangeListDetail">
        <div class="item">{{item.expenditure}}</div>
        <div class="item">{{item.accountBook}}</div>
      </div>
    </div>




  </div>
</template>

<style scoped>
  .demo{
    width: 360px;
    height: 180px;
    background: #F0FAFF;
    margin-left: -180px;
    margin-top: -220px;
    border-radius: 5px;
    border: 1px solid #90CCE8;
    box-shadow: 0 0 10px rgba(0,0,0,0.2);
    overflow: hidden;
    color: #333333;
  }
  .popover-head{
    width: 100%;
    height: 40px;
    line-height: 40px;
    background: #F0FAFF;
    font-size: 14px;
    border-bottom: 1px solid #C5E2F0;
  }
  .popover-head i{          /*头关闭按钮*/
    float: right;
    color: #A1C1E2;
    font-size: 12px;
    margin-top: 13px;
    margin-right: 12px;
    cursor: pointer;
  }
  .popover-head .title{
    margin-left: 15px;
    font-weight: bold;
  }
  .popover-head .small-title{
    font-size: 12px;
    color: #999999;
    font-weight: normal;
  }
  .popover-main{
    padding: 20px 12.5px;
    width: calc(100% - 25px);
    height: 100px;
    overflow: auto;
  }
  .popover-main .item-list{
    height: 30px;
    width: auto;
    background: #ffffff;
    border-left: 1px solid #E7ECF1;
    border-right: 1px solid #E7ECF1;
    border-bottom: 1px solid #E7ECF1;
    display: flex;
    line-height: 30px;
    flex-direction: row;
  }
  .popover-main .item-list-head{
    height: 30px;
    width: auto;
    background: #F1F4F7;
    border: 1px solid #E7ECF1;
    display: flex;
    line-height: 30px;
    flex-direction: row;
  }
  .popover-main .item{
    flex: 1;
    padding-left: 5px;
  }
  .popover-main .box-top{
    width: 100%;
    padding-bottom: 15px;
    border-bottom: 1px solid #C5E2F0;
  }
  /*---------↓*/

  .option{
    height:34px;
    /*background:#00ff00;*/
    margin-top:10px;
    width:100%;
    float:left;
  }
  .wordtype{
    font-size:12px;
    line-height:18px;
    font-family: Helvetica Neue,"微软雅黑","黑体";
    color:#F44848;
    float:left;
  }



  /*---------↑*/
  .table-head{
    display: flex;
    flex-direction: row;
    height: 28px;
    line-height: 28px;
    background: #F1F4F7;
    border: 1px solid #E7ECF1;
  }
  .table-head .table-list-head{
    display: flex;
    flex-direction: row;
  }
  .table-box{
    height: 56px;
    overflow: hidden;
    background: #ffffff;
    display: flex;
    flex-direction: row;
    border-left: 1px solid #E7ECF1;
    border-right: 1px solid #E7ECF1;
    border-bottom: 1px solid #E7ECF1;
  }
  .table-list-head{
    flex: 2;
  }
  .table-box .table-list-head{
    height: 28px;
  }
  .table-list-head-all{
    width: 100%;
    float: left;
    height: 28px;
    line-height: 28px;
    display: flex;
    flex-direction: row;
    border-bottom: 1px solid #E7ECF1;
  }
  .table-list-footer{
    flex: 1;
    display: flex;
    flex-direction: row;
    line-height: 28px;
  }
  .table-list-footer-big .head-item{
    height: 56px;
    line-height: 56px;
    text-align: center;
    border-left: 1px solid #E7ECF1;
  }
  .head-item{
    flex: 1;
    text-align: center;
  }
  .blue{
    cursor: pointer;
    color: #1476CC;
  }
  .big{
    flex: 2;
  }
  .table-list{
    width: 100%;
    display: flex;
    height: 28px;
    line-height: 28px;

    flex-direction: row;
    background: #ffffff;
    border-bottom: 1px solid #E7ECF1;
  }
  .popover-main .title{
    margin: 15px 0 12px 0;
    font-weight: 500;
  }
</style>
<script>
  import { mapActions } from 'vuex'
  import { mapGetters } from 'vuex'
  export default {
    data() {
      return {

      };
    },
    computed:{
      ...mapGetters([
        'balanceCredit','balanceChangeListDetail'
      ])
    },
    methods: {
      close: function () {
        alert(0)
      },
      time(times){
        if(times.effectiveDate && times.expireDate){
          return times.effectiveDate.substring(0,4)+'.'+times.effectiveDate.substring(4,6)+'.'+times.effectiveDate.substring(6,8)+'~'+times.expireDate.substring(0,4)+'.'+times.expireDate.substring(4,6)+'.'+times.expireDate.substring(6,8);
        }else{
          return '';
        }

      },
      ...mapActions([
        'popoverAlert'
      ])
    }
  };
</script>
