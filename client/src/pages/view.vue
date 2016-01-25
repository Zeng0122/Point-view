<template xmlns:v-bind="http://www.w3.org/1999/xhtml" xmlns:v-on="http://www.w3.org/1999/xhtml">
  <div class="am-g">
    <div class="am-u-md-3">
      <div class="product-left am-u-md-10">
        <h3 class="hot-st am-text-center">正餐菜单</h3>
        <ul class="list">
          <li><a href="#hot-view">促销和热卖产品</a></li>
          <li><a href="#drink-view">饮品</a></li>
        </ul>
      </div>
      <div class="product-left am-u-md-11">
        <h3 class="hot-st am-text-center">购物车</h3>
        <div class="am-g">
          <div class="am-u-md-11 am-u-md-centered">
            <table class="am-table am-table-bordered am-table-compact am-table-centered am-text-middle"
            <tr>
              <th>食物名称</th>
              <th>价格</th>
            </tr>
            <template>
              <tr>
                <td class="am-text-middle">
                  <p class="am-margin-top"></p>
                </td>
                <td class="am-text-middle">
                  <p class="am-margin-top"></p>
                </td>
              </tr>
            </template>
            </table>
            <button class="v-bud am-fr">取消</button>
            <button class="v-bud am-fl">确定</button>
          </div>
        </div>
      </div>
    </div>
    <div class="am-u-md-9">
      <h2>促销和热卖产品</h2>
      <ul id="hot-view", class="am-nav am-nav-pills">
        <template v-for="item in list">
          <li class="v-lis am-margin-bottom-xl" width="300">
            <div>
              <img src="1.png", width="250px", height="100px" >
              <p class="am-margin-sm">{{item.name}}</p>
              <p class="am-cf am-margin-sm">
                <span class="am-fl">{{item.price}}</span>
                <span class="am-fr">已售：{{item.count}}</span>
              </p>
              <button id="{{item.viewID}}" class="v-bud am-fr">添加</button>
            </div>
          </li>
        </template>
      </ul>
      <h2>饮品</h2>
      <ul id="drink-view", class="am-nav am-nav-pills">
        <template v-for="item in listdrink">
          <li class="v-lis am-margin-bottom-xl" width="300">
            <div>
              <img src="1.png", width="250px", height="100px" >
              <p class="am-margin-sm">{{item.name}}</p>
              <p class="am-cf am-margin-sm">
                <span class="am-fl">{{item.price}}</span>
                <span class="am-fr">已售：{{item.count}}</span>
              </p>
              <button id="{{item.viewID}}" class="v-bud am-fr">添加</button>
            </div>
          </li>
        </template>
      </ul>
    </div>
  </div>
</template>
<style>
  ul.list li {
    padding: 10px;
    color: #eee;
  }
  ul.list li a { color: #333;}
  ul.list li a:hover { color: #f00;}
  .product-left {
    background-color: #efaf00;
    margin: 10px;
    border-radius: 10px;
    margin-bottom: 100px;
  }
  .hot-st {
    border-bottom: 2px solid #fff;
    padding: 10px;
    color: #efefef;
  }
  .v-lis {
    margin-right: 30px;
    border: 1px solid #eee;
    border-radius: 3px;
  }
  .v-bud {
    color: #fff;
    background-color: #f00;
    border: none;
    border-radius: 5px;
    padding: 5px 15px 5px 15px;
    margin: 5px 5px 10px 5px ;
  }
</style>
<script>
var tools = require("../tools");
module.exports = {
  data:function(){
  return{
    list: [{
        name:'1',
        price: '¥12.00',
        count: '122'
      },{
        name:'2',
        price: '¥22.00',
        count: '132'
      },{
        name:'3'
      }],
    listdrink: [{
        name:'1',
        price: '¥12.00',
        count: '122'
      },{
        name:'2'
      }]
  }
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
  },
  created:function() {
      var $this = this;
    $this.$http.get(tools.resolveUrl("/Users"), {

    }, function (data, status, request) {

      // $this.list=[{name:3}]
    }).error(function (data, status, request) {

    })
  }
}
</script>
