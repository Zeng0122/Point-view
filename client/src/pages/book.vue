<template xmlns:v-bind="http://www.w3.org/1999/xhtml" xmlns:v-on="http://www.w3.org/1999/xhtml">
  <div class="am-container">
    <div class='am-g'>
      <div class='am-u-sm-11 am-u-md-8 am-u-lg-7 am-u-sm-centered'>
        <form class="am-form" data-am-validator="true" id="new_user" action="/users" accept-charset="UTF-8" method="post">
          <fieldset>
            <h2>个人信息（必填）</h2>
            <div class="am-form-group">
              <div class="field_with_errors">
                <label for="user_name">姓名</label>
              </div>
              <div class="field_with_errors">
                <input class="am-radius" required="required" type="text" value="" name="user[name]" id="user_name" />
              </div>
            </div>
            <div class="am-form-group">
              <div class="field_with_errors">
                <label for="user_phone">联系电话</label>
              </div>
              <div class="field_with_errors">
                <input class="am-radius" required="required" type="text" value="" name="user[phone]" id="user_phone" />
              </div>
            </div>
            <h2>个人帐号（必填）</h2>
            <div class='am-form-group'>
              <div class="field_with_errors">
                <label for="user_email">邮箱</label>
              </div>
              <div class="field_with_errors">
                <input class="am-radius" required="required" type="email" value="" name="user[email]" id="user_email" />
              </div>
              <p class='am-form-help'>此邮箱将作为您的登陆账号</p>
            </div>
            <div class='am-form-group'>
              <div class="field_with_errors">
                <label for="user_password">密码</label>
              </div>
              <div class="field_with_errors">
                <input class="am-radius" required="required" type="password" name="user[password]" id="user_password" />
              </div>
              <p class='am-form-help'>请使用 8-16 位，由大写字母、小写字母、阿拉伯数字和特殊符号中至少 3 种组合而成的密码</p>
            </div>
            <div class='am-form-group'>
              <label for="user_password_confirmation">确认密码</label>
              <input class="am-radius" required="required" type="password" name="user[password_confirmation]" id="user_password_confirmation" />
            </div>
            <hr>
            <p class='am-text-sm'>点击“注册帐号”按钮，表示您了解并同意我们的
              <a target="_blank" href="/help/articles/115198">服务条款</a>
            </p>
            <hr>
            <div class='am-form-group'>
              <input type="submit" name="commit" value="注册帐号" class="am-btn am-btn-block am-btn-success am-radius" />
            </div>
        </form>
      </div>
    </div>
  </div>
</template>
