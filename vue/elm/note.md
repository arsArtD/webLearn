#20180107#
>
>写于： 1/8/2018 9:51:08 AM 
----------

* vue front-elm初始化
>
>npm install vue-cli
>
>vue init 
>
>(执行上述步后会自动加载vue, vue-router)
>
>npm install better-scroll fastclick iscroll showdown vuex
>
* 代码执行的问题：
>
>关闭eslint front-elm\config\index.js 中 useEslint设置为false
>
>打开eslint 会报很多关于格式的问题，如：indent,文件尾部换行等，强制要求tab为两个空格

* 写路由的的一些问题:
  初始化 router的时候：

  const router = new VueRouter({
   routes: routers,
   mode: 'history',
   //strict : true
  })

routes对应的value值的名称如果不是 routes不能够简写

  new Vue({
  router,
}).$mount('#app')
> 中的router应该为VueRouter的实例

* 首页空白的问题：
需要在index.html中：
  `<div id="app"></div>`
修改为
   `<div id="app"><router-view/></div>`

#20180128

 This dependency was not found:

* !!vue-style-loader!css-loader?{"minimize":false,"sourceMap":false}!../../node_modules/vue-loader/lib/style-compiler/index?{"vue":true,"id":"data-v-1d57e5ea","scoped":false,"hasInlineConfig":false}!stylus-loader?{"sourceMap":false}!../../node_modules/vue-loader/lib/selector?type=styles&index=0!./a.vue in ./src/components/a.vue

To install it, you can run: npm install --save !!vue-style-loader!css-loader?{"minimize":false,"sourceMap":false}!../../node_modules/vue-loader/lib/style-compiler/index?{"vue":true,"id":"data-v-1d57e5ea","scoped":false,"hasInlineConfig":false}!stylus-loader?{"sourceMap":false}!../../node_modules/vue-loader/lib/selector?type=styles&index=0!./a.vue

解决步骤：
当前目录（项目）下：
npm install node-sass sass-loader scss scss-loader --save-dev
npm install -g cnpm --registry=https://registry.npm.taobao.org
cnpm install node-sass

#20180204
代理服务: 在config.index中添加如下内容

```javascript
const proxypath = 'http://localhost:8001'

let proxyTable = {};
context.map(function(item, index, array){
  proxyTable[item] = {
    target: proxypath,
    changeOrigin : true
  }
})

console.log(proxyTable);
```
并修改fetch.js引用的baseUrl : config/env.js
后续需要根据实际环境来设置proxypath和baseUrl

> 字体过小： 在main.js 中引入rem.js
> ul 样式错乱, 需要在app.vue中引入common.scss