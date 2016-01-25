<template xmlns:v-bind="http://www.w3.org/1999/xhtml" xmlns:v-on="http://www.w3.org/1999/xhtml">
  <div class="am-collapse am-topbar-collapse">
    <ul class="am-nav am-nav-pills am-topbar-nav">
      <li v-link="{name:'home', activeClass: 'am-active'}">
        <a>首页</a>
      </li>
      <li v-link="{name:'view', activeClass: 'am-active'}">
        <a>浏览菜单</a>
      </li>
      <li v-link="{name:'account', activeClass: 'am-active'}">
        <a>我的帐户</a>
      </li>
      <li v-link="{name:'need', activeClass: 'am-active'}">
        <a>帮助</a>
     </li>
    </ul>

    <div class="am-topbar-right">
      <ul class="am-nav am-nav-pills am-topbar-nav">
        <template v-if="userInfo.loginName">
           <li><a>{{userInfo.loginName}}</a></li>
           <li>
             <div style="margin-top:12px" v-on:click="logout()">注销</div>
            </li>
        </template>
        <template v-else>
          <li>
            <div style="margin-top:12px" v-link="{name:'login', activeClass: 'am-active'}"><a>登录</a></div>
          </li>
        </template>
        <li style="margin-top:12px">|</li>
        <li v-link="{name:'help', activeClass: 'am-active'}"><a>追踪订单</a></li>
      </ul>
    </div>
  </div>
</template>
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
    methods:{
      logout:void(0)
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
