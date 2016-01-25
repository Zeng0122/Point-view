<template xmlns:v-on="http://www.w3.org/1999/xhtml">
  <div class='am-container'>
    <div class='am-u-md-5 am-u-sm-centered'>
      <h1>登陆系统</h1>
      <form class="am-form" data-am-validator="true" accept-charset="UTF-8" v-on:submit.prevent="login">
        <div class='am-form-group'>
          <label for="username">账号</label>
          <input class="am-radius" required="required" type="text" v-model="username" id="username"/>
        </div>
        <div class='am-form-group'>
          <label for="password">密码</label>
          <input class="am-radius" required="required" type="password" v-model="password" id="password"/>
        </div>
        <div class="am-g am-margin-top-xl">
          <div class='am-form-group am-u-md-6'>
            <input type="submit" name="commit" value="登陆" id="sessions-new-login-btn"
                   class="am-btn am-btn-block am-btn-primary am-radius"/>
          </div>
          <div class='am-form-group am-u-md-6'>
            <input type="submit" value="注册" id="sessions-new-help-btn" v-link="{name:'book', activeClass: 'am-active'}"
                   class="am-btn am-btn-block am-btn-success am-radius"/>
          </div>
        </div>
        <div style="height: 100px"></div>
      </form>
    </div>
  </div>
</template>
<script>
  var tools = require("../tools");
  var auth = require("../auth");
  module.exports = {
    data: {
      username: null,
      password: null
    },
    methods: {
      login: function () {
        var $this = this;
        $this.$http.post(tools.resolveUrl("/Users/login"), {
          username: $this.username,
          password: $this.password
        }, function (data, status, request) {
          auth.login(data.userInfo)
          $this.$dispatch('link', "root");
        }).error(function (data, status, request) {

        })
      }
    }
  }
</script>
