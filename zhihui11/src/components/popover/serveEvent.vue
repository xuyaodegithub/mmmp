<template>
  <div class="demo serveEvent">
      <div class="popover-head">
          <span class="title">服务性事件</span><span class="small-title"></span><i v-on:click="popoverAlert()" class="el-icon-close"></i>
      </div>
      <div class="popover-main">
        <p class="row"><span class="title">事件名称：</span><span class="info">温州未实名号码关停</span></p>
        <p class="row"><span class="title">事件描述：</span><span class="info">针对未实名等级客户进行关停（平台显示实名状态为“是”，实际为非实名）</span></p>
        <p class="row"><span class="title koujin-tit">事件口径：</span><span class="info koujin-info">经查您的号码未经过身份验证核验，根据国家对实名制规定要求将被依法停机，请您到电信自有
营业厅进行实名核验，感谢您的支持。</span></p>
        <p class="row"><span class="title">操作方法：</span><span class="info">根据统一口径解释、引导</span></p>
      </div>
      <div class="btn-box">
        <span>用户是否认可</span>
        <el-select v-model="isAccept" placeholder="--">
          <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value">
          </el-option>
        </el-select>
        <el-button type="info" :disabled="dis">投诉派单</el-button>
      </div>
  </div>
</template>

<style scoped>
  .demo{
    width: 599px;
    background: #F0FAFF;
    margin-left: -300px;
    margin-top: -150px;
    border-radius: 5px;
    border:1px solid #90CCE8;
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
  .popover-head i{
      float: right;
      color: #A1C1E2;
      font-size: 12px;
      margin-top: 13px;
      margin-right: 12px;
      cursor: pointer;
  }
  .popover-head .title{
      margin-left: 12px;
      font-weight: bold;
  }
  .popover-main{
    padding: 10px 0 15px 0;
    border-bottom: 1px solid #C5E2F0;
  }
  .popover-main .row{
    margin-left: 15px;
    margin-top: 10px;
  }
  .popover-main .row.koujin{
    margin-top: 4px;
  }
  .popover-main .row span{
    display: inline-block;
  }
  .koujin-tit{
    transform: translateY(-17px);
  }
  .popover-main .row .info{
    width: 504px;
  }
  .popover-main .row .koujin-info{
    line-height: 18px;
  }
  .btn-box{
    height: 28px;
    margin: 10px 0 18.5px 14.5px;
  }
  .btn-box .el-input .el-input__inner{
    width: 64px;
    height: 28px!important;
  }
</style>
<style>
  .serveEvent .el-select{
    width: 64px;
    margin-left: 6px;
  }
  .serveEvent .el-input__inner{
    height: 28px;
  }
  .serveEvent .el-select-dropdown__item{
    padding: 0 10px;
    height: 24px;
    line-height: 24px;
  }
  .serveEvent .el-button{
    width: 64px;
    height: 28px;
    line-height: 28px;
    padding: 0;
    font-size: 12px;
    margin-left: 20px;
    font-weight: 100;
  }
</style>
<script>
  import { mapActions } from 'vuex'
  import { mapGetters } from 'vuex'
  export default {
    data() {
      return {
          isAccept:'',
          options:[{
              value: 'yes',
              label: '是'
          },{
              value: 'no',
              label: '否'
          }],
          dis: false
      };
    },
    methods: {
      close: function () {
        alert(0)
      },
      ...mapActions([
        'popoverAlert'
      ]),
      ...mapGetters([
        'popoverAlive'
      ])
    }
  };
</script>
