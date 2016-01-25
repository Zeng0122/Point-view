<template xmlns:v-bind="http://www.w3.org/1999/xhtml" xmlns:v-on="http://www.w3.org/1999/xhtml">
  <div class="bg-img am-text-center">
    <div v-if="userInfo.loginName">
      <p class="test"></p>
      <a v-link="{name:'view', activeClass: 'am-active'}" class="tes am-text-xxxl">{{userInfo.loginName}},开始点餐>>></a>
    </div>
    <div v-else>
      <p class="test"></p>
      <a v-link="{name:'login', activeClass: 'am-active'}" class="tes am-text-xxxl">欢迎点餐.请登录>>></a>
    </div>
  </div>
</template>
<style>
  .bg-img {
    background: url("1.png") center center;
    height: 500px;
  }
  .test {
    padding-top: 200px;
    display: block;
  }
  .tes {
    color: #f00;
  }
</style>
<script>
  var tools = require("../tools");
  var auth = require("../auth");
  module.exports = {
    created: function () {
      var $this=this;
      auth.valid($this, function () {
        $this.userInfo=tools.getUserInfo();
      }, function () {

      });
    },
    data: function () {
     var $this=this;
      $this.userInfo={};

      return {
        userInfo:$this.userInfo
      };
    }
  }
</script>
