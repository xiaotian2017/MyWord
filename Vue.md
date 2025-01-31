# <center><font color='red'>Vue</font></center>

##一、搭建Vue项目
>使用Vue-cli 3.0 搭建Vue项目

> ### Vue CLI介绍
> Vue CLI是一个基于Vue.js进行 快速开发的完整系统，提供：
>* 通过`@vue/cli`搭建交互式的项目脚手架
>* 通过`@vue/cli + @vue/cli-service-global`快速开始零配置原型开发
>* 运行时依赖`@vue/cli-service`，该依赖：
>   * 可升级
>   * 基于`webpack`构建，并带有合理的默认配置
>   * 可以通过项目内的配置文件进行配置
>   * 可以通过插件进行扩展
>   * 一个丰富的官方插件集合，集成了前端生态中最好的工具
><p> Vue CLI致力于将Vue生态中的工具基础标准化。它确保了各种构建工具能够基于智能的默认配置即可平稳衔接，这样你可以专注于撰写应用上，而不必花好几天去纠结配置的问题。与此同时，它也为每个工具提供了调整配置的灵活性，无需eject</p>

###1.环境准备:
1. **安装Node.js**
2. **安装vue-cli 3.0**
> 如果有安装vue-cli旧版本可能会导致安装vue-cli新版本报错
解决方案：
将C:\Users\STL\AppData\Roaming\npm文件下的node_modules文件夹删除，即可重新安装新版本vue-cli
```
npm install -g @vue/cli
```

###2.创建项目
>vue-cli搭建脚本文件,创建项目(项目名称不能包含大写字母)
>以搭建一个项目名称为vue-demo的Vue前端项目为例

在终端输入一下命令:
```
vue create vue-demo
```
根据提示进行相应的配置（以手动配置为例）：

**选择`Manually select features`(手动配置)**

![Manually select features](https://upload-images.jianshu.io/upload_images/1196972-d73a587f46e9d558.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/650/format/webp "手动配置")

**选择项目需要的一些特性（此处我们选择需要Babel编译、使用Vue路由、Vue状态管理器、CSS预处理器、代码检测和格式化、以及单元测试，暂时不考虑端到端测试(E2E Testing)）**

![texing](https://upload-images.jianshu.io/upload_images/1196972-7b1a2fc2c1779576.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/887/format/webp "特性")

**选择CSS预处理器语言，此处选择LESS**

![less](https://upload-images.jianshu.io/upload_images/1196972-d2be541d362b1662.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/952/format/webp "LESS")

**选择ESLint的代码规范，此处使用 Standard代码规范**

![ESLint](https://upload-images.jianshu.io/upload_images/1196972-cf85c45a5d432058.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/965/format/webp "ESLint代码规范")

**选择何时进行代码检测，此处选择在保存时进行检测**

![lint on save](https://upload-images.jianshu.io/upload_images/1196972-42088b0085a848c9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/923/format/webp "代码检测")

**选择单元测试解决方案，此处选择 Jest**

![Jest](https://upload-images.jianshu.io/upload_images/1196972-e631d9f71ab1e18a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/901/format/webp "Jest单元测试")

**选择 Babel、PostCSS、ESLint等配置文件存放位置，此处选择单独保存在各自的配置文件中**

![dedicated config files](https://upload-images.jianshu.io/upload_images/1196972-5dad67c616d6dc0c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/942/format/webp "保存在各自的配置文件")


**配置完成后等待Vue-cli完成初始化**

![Initialize the](https://upload-images.jianshu.io/upload_images/1196972-c27e74c06fadc518.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/826/format/webp "初始化")

**vue-cli初始化完成后，根据提示，进入到项目vue-demo项目中，并启动项目**
```
//进入到vue-demo项目
cd vue-demo
//启动服务
npm run serve
```

##二、Vue生命周期
1. `beforeCreate`
    > 实例创建之前调用
  

2. `created`
    > 实例创建成功，此时 data 中的数据显示出来了。
    >在这一步主要的工作为：调用数据，调用方法，调用异步函数。

3. `beforeMount`
    > 数据中的 data 在模版中先占一个位置。
    > 在挂载开始之前被调用：render 函数或者模板首次被调用。

4. `mounted`
    > 模版中的 data 数据直接显示出来了。
    >`el` 被新创建的 `vm.$el` 替换，并挂载到实例上去之后调用该钩子。这个时候DOM会被渲染完成，初始的数据会被渲染完成，在这里才能获取到具体的DOM元素。

5. `beforeUpdate`
    > 数据更新时调用，发生在虚拟 DOM 重新渲染之前。 你可以在这个钩子中进一步地更改状态，这不会触发附加的重渲染过程。 当我们更改Vue的任何数据，都会触发该函数。

6. `updated`
    > 由于数据更改导致的虚拟 DOM 重新渲染，在这之后会调用该钩子。 当这个钩子被调用时，组件 DOM 已经更新，所以你现在可以执行依赖于 DOM 的操作。然而在大多数情况下，你应该避免在此期间更改状态，因为这可能会导致更新无限循环。 该钩子在服务器端渲染期间不被调用。

7. `beforeDestroy`
    > 实例销毁之前调用。在这一步，实例仍然完全可用。

8. `destroyed`
    > Vue 实例销毁后调用。调用后，Vue 实例指示的所有东西都会解绑定，所有的事件监听器会被移除，所有的子实例也会被销毁。 该钩子在服务器端渲染期间不被调用。


##三、模板语法
`<span>Message: {{ msg }}</span>`
```
<!-- 行内样式： -->
<h1 :style="{color:'red','font-weight':200}">这是一个H1</h1>
```

##四、Vue指令
Vue 为 `v-bind` 和 `v-on` 这两个最常用的指令，提供了特定简写：

`v-bind` 缩写
```
<!-- 完整语法 -->
<a v-bind:href="url">...</a>

<!-- 缩写 -->
<a :href="url">...</a>
```

`v-on` 缩写
```
<!-- 完整语法 -->
<a v-on:click="doSomething">...</a>

<!-- 缩写 -->
<a @click="doSomething">...</a>
```

###1.`v-bind`:
> `v-bind`指令用于给`html`标签设置属性。

```
<span :text="content">使用</span>

<!-- 会渲染成如下: -->

<span text="content">使用</span>
```

三元表达式：

```
<div v-bind:class="[isActive ? activeClass : '', errorClass]"></div>
```
这样写将始终添加 `errorClass`，但是只有在 `isActive` 是 `truthy` 时才添加 `activeClass。`
> `truthy`（真值）指的是在布尔值上下文中，转换后的值为真的值。所有值都是真值，除非它们被定义为 假值（即除 `false`、`0`、`""`、`null`、`undefined` 和 `NaN` 以外皆为真值）。


###2.`v-if`、`v-else`:
> 条件渲染;`v-if` 指令用于条件性地渲染一块内容。这块内容只会在指令的表达式返回 `truthy` 值的时候被渲染。

```
<h1 v-if="awesome">Vue is awesome!</h1>
<h1 v-else>Oh no 😢</h1>
```
`v-else` 元素必须紧跟在带 `v-if` 或者 `v-else-if` 的元素的后面，否则它将不会被识别。

###3.`v-show`:
> 用法与`v-if`大致一致；不同的是带有 `v-show` 的元素始终会被渲染并保留在 DOM 中。`v-show` 只是简单地切换元素的 CSS 属性 `display`。

```
<h1 v-show="error">Error!</h1>
...
data(){
  return{
    error:false
  }
}

<!-- 会渲染成如下: -->

<h1 style="display: none;">Error!</h1>
```

###4.`v-for`:
> 可以用 `v-for` 指令基于一个数组来渲染一个列表;
`v-for`具有比 `v-if` 更高的优先级

```
<ul id="example-1">
  <li v-for="(item, index) in items">
    {{ index }}:{{ item.message }}
  </li>
</ul>
...
data(){
  return{
    items: [
      { message: 'Foo' },
      { message: 'Bar' }
    ]
  }
}
```

也可以用 `of` 替代 `in` 作为分隔符，因为它更接近 `JavaScript` 迭代器的语法：
`<div v-for="item of items"></div>`

也可以用 `v-for` 来遍历一个对象的属性:
```
<ul id="v-for-object" class="demo">
  <li v-for="value in object">
    {{ value }}
  </li>
</ul>
...
data(){
  return{
    object: {
      title: 'How to do lists in Vue',
      author: 'Jane Doe',
      publishedAt: '2016-04-10'
    }
  }
}
```

也可以提供第二个的参数为 `property` 名称 (也就是键名)：
```
<div v-for="(value, name) in object">
  {{ name }}: {{ value }}
</div>
```

还可以用第三个参数作为索引：
```
<div v-for="(value, name, index) in object">
  {{ index }}. {{ name }}: {{ value }}
</div>
```

###5.`v-on`:
> 用 `v-on` 指令监听 DOM 事件
`<button v-on:click="counter += 1">Add</button>`

```
<div id="example-2">
  <!-- `greet` 是在下面定义的方法名 -->
  <button v-on:click="greet">Greet</button>
</div>
```

**事件修饰符**
>修饰符是由点开头的指令后缀来表示的。
* `.stop`
* `.prevent`
* `.capture`
* `.self`
* `.once`
* `.passive`

```
<!-- 阻止单击事件继续传播 -->
<a v-on:click.stop="doThis"></a>

<!-- 提交事件不再重载页面 -->
<form v-on:submit.prevent="onSubmit"></form>

<!-- 修饰符可以串联 -->
<a v-on:click.stop.prevent="doThat"></a>

<!-- 只有修饰符 -->
<form v-on:submit.prevent></form>

<!-- 添加事件监听器时使用事件捕获模式 -->
<!-- 即元素自身触发的事件先在此处理，然后才交由内部元素进行处理 -->
<div v-on:click.capture="doThis">...</div>

<!-- 只当在 event.target 是当前元素自身时触发处理函数 -->
<!-- 即事件不是从内部元素触发的 -->
<div v-on:click.self="doThat">...</div>
```

>使用修饰符时，顺序很重要；相应的代码会以同样的顺序产生。
因此，用 `v-on:click.prevent.self` 会阻止所有的点击，
而 `v-on:click.self.prevent` 只会阻止对元素自身的点击。

###6.`v-model`:
>可以用 `v-model` 指令在表单 `<input>`、`<textarea>` 及 `<select>` 元素上创建双向数据绑定。

`v-model` 会忽略所有表单元素的 `value、checked、selected` 特性的初始值而总是将 Vue 实例的数据作为数据来源。你应该通过 `JavaScript` 在组件的 `data` 选项中声明初始值。

```
<input v-model="message" placeholder="edit me">
<p>Message is: {{ message }}</p>
```

##五、绑定动态样式
```
<div
  :class="[treatmentValue.indexOf(item) > -1?'treatments-li-select':'treatments-li']"
>
</div>
```

##六、父子组件
1.父 => 子（传值）
```
<!-- 父组件： -->
静态值：title = 'My Journey with Vue'
动态值：v-bind:title="title"
...
data() {
  return {
    title: 'title name'
  };
},

<!-- 子组件： -->
<span>{{title}}</span>
...
<!-- 这个 prop 用来传递一个初始值；这个子组件接下来希望将其作为一个本地的 prop 数据来使用。在这种情况下，最好定义一个本地的 data 属性并将这个 prop 用作其初始值： -->
props:['title'],
```

2.子 => 父（传值）
```
<!-- 父组件： -->
@childFn="parentFn"
子组件传来的值 : {{message}}
...
data: {
    message: ''
},
methods: {
    parentFn(payload) {
    this.message = payload;
  }
}

<!-- 子组件： -->
<input type="text" v-model="message" />
<button @click="click">Send</button>
...
data() {
    return {
      // 默认
      message: '我是来自子组件的消息'
    }
},
methods: {
  click() {
        this.$emit('childFn', this.message);
    }
}   
```

3.子组件调用父组件方法
```
<!-- 父组件： -->
<child @fatherMethod="fatherMethod"></child>
...
method:{
    fatherMethod(){
        //方法体
    }
}

<!-- 子组件： -->
<button @click="childMethod()">点击</button>
...
methods: {
    childMethod() {
        this.$emit('fatherMethod');  //使用$emit()引入父组件中的方法
    }
},
```

4.父组件调用子组件方法
```
<!-- 父组件： -->
button v-on:click="clickParent">点击</button>
<child1 ref="child1"></child1>
...
methods: {
    clickParent() {
        this.$refs.child1.handleParentClick("val");//val为子组件传给父组件的值
    }
}

<!-- 子组件： -->
methods: {
    handleParentClick(e) {
    }
}
```
5.跨路由方法调用
```
<router-view ref="main" />

...

methods: {
  // 调用其他路由里面的方法
  hireNumFun(){
    this.$refs['main'].hireNumFun()
  },
}
```

##七、数据监听
```
data(){
  return{
    age:'',
    ruleForm:{
      time:''
    }
  }
},
watch:{
  age(val,oldVal){//普通的watch监听
    console.log(val,oldVal)
  },
  'ruleForm.time':{//深度监听，可监听到对象、数组的变化
    handler(val,oldVal){
      console.log(val,oldVal)
    }
  }
},
```

##八、Vue-router
###1.安装
>一般在创建项目时已经安装·，可跳过此步骤

`npm install vue-router  --save-dev`

###2.新建`router`目录
src目录下新建`router.js`文件
```
import Vue from 'vue'
import Router from 'vue-router'

Vue.use(Router)

export default new Router({
  routes: [
    {
      path: '/',
      name: 'home',
      component: () => import('./views/Home.vue')
    },
    {
      path: '/releasedjob',
      name: 'releasedjob',
      component: () => import('./views/ReleasedJob.vue')
    },
    {
      path: '/membermanage',
      name: 'membermanage',
      component: () => import('./views/MemberManage.vue')
    },
    {
      path: '*',
      redirect: '/'
    }
  ]
})
```

###3.`main.js`中引入
```
import router from './router'

...

new Vue({
  router,
  store,
  el: '#app',
  render: h => h(App)
}).$mount('#app')
```

###4.路由跳转

路由渲染：`<router-view />`

跳转方式：
* `<router-link to=""></router-link>`
* `this.$router.push({path:''})`

###5.动态路由
>动态路由路径参数，以冒号开头
```
routes: [
    {
      path: '/helloworld/:id',
      name: 'helloworld',
      component: () => import('./views/Helloworld.vue')
    },
  ]
```
**获取路由的参数**
```
mounted(){
  console.log(this.$route.params.id)
}
```

###6.路由钩子

* `router.beforeEach(function(to,form,next){})`//在跳转之前执行
* `router.afterEach(function(to,form))`//在跳转之后判断


**`beforeEach`函数有三个参数：**
* `to:router`即将进入的路由对象
* `from`:当前导航即将离开的路由
* `next:Function`,进行管道中的一个钩子，如果执行完了，则导航的状态就是 `confirmed` （确认的）；否则为`false`，终止导航。

**`afterEach`函数不用传`next()`函数**


`main.js`中：
```
new Vue({
  router,
  store,
  el: '#app',
  render: h => h(App)
}).$mount('#app')

router.beforeEach((to, from, next) => {
  let token = router.app.$storage.fetch("token");
  let needAuth = to.matched.some(item => item.meta.login);
  if(!token && needAuth) return next({path: "/login"});
  next();
})
```


###7.路由嵌套
```
routes: [
  {
    path: '/helloworld',
    name: 'helloworld',
    component: () => import('./views/Helloworld.vue'),
    children:[
      {
        path:'view1',
        name:'view1',
        component:view1
      },
      {
        path:'view2',
        name:'view2',
        component:view2
      }
    ]
  },
]
```

###8.过渡效果
`<router-view>`是基本的动态组件，所以可以用`<transition>`组件给它添加一些过渡效果：
```

<transition name='fade-transform' mode="out-in">
  <router-view />
</transition>

...

<style scoped>
  .fade-transform-leave-active,
  .fade-transform-enter-active {
    transition: all .5s;
  }

  .fade-transform-enter {
    opacity: 0;
    transform: translateX(-30px);
  }

  .fade-transform-leave-to {
    opacity: 0;
    transform: translateX(30px);
  }
</style>
```
* `mode="in-out"`:新元素先进行过度，完成之后当前元素过度离开。
* `mode="out-in"`:当前元素先进行过度，完成之后新元素过度进入。
* `fade-enter`:进入过渡的开始状态，元素被插入时生效，只应用一帧后立刻删除。
* `fade-enter-active`:进入过渡的结束状态，元素被插入时就生效，在过渡过程完成后移除。
* `fade-leave`:离开过渡的开始状态，元素被删除时触发，只应用一帧后立刻删除。
* `fade-leave-active`:离开过渡的结束状态，元素被删除时生效，离开过渡完成后被删除。

###9.监听路由
```
watch:{
  // 如果路由有变化，会再次执行该方法
  '$route':'fetchData'
},
methods:{
  fetchData(){
    console.log('fetchData')
  }
}
```


##九、Vuex
> 新建一个store.js：
```
import Vue from 'vue'
import Vuex from 'vuex'

Vue.use(Vuex)

export default new Vuex.Store({
  state: {
    storeMsg:'store计数器',
    storeCount:0
  },
  mutations: {
    del(state,payload){
      state.storeCount--
    },
    add(state,payload){
      state.storeCount++
    }
  },
  actions: {

  }
})
```
actions为数据请求方法，例fun函数：
```
fun(context,payload){
  ...数据请求
  context.commit('mutations方法名',参数)
}
```
Action 通过 store.dispatch 方法触发：
```
store.dispatch('increment')
```

>vue模板文件：
```
<template>
  <div class="storeCount">
    <span>{{storeMsg}}：</span>
  
    <button class="btn" @click="del()">-</button>
    <span class="count">{{storeCount}}</span>
    <button class="btn" @click="add()">+</button>

  </div>
</template>

<script>
import {mapState,mapMutations,mapActions} from 'vuex';
export default {
  name: "vue",
  data() {
    return {
    };
  },
  computed:{
      ...mapState(['storeMsg','storeCount'])
      <!-- this.$store.state.storeMsg -->
  },
  methods: {
      ...mapMutations(['add','del']),
      <!-- this.$store.commit('add') -->
      <!-- ...mapActions('命名空间',['action方法名']) -->
  }
};
</script>
```


##十、发布到Tomcat
1. 在`config`中的`index.js`下修改`webpack`配置(两处)：
    ```
    assetsPubilcPath:'/my-project/',
    ```

2. 使用`npm run build`将项目打包

3. 把打包后的`dist`文件夹更名为`package.json`中`name`参数名，放到`tomcat`中`webapps`中

4. 开启服务器访问`localhost:8080/项目名`即可以看到你的项目内容


##十一、Vue打包优化

1. **方法一：引入 `cdn` 资源**
    * 在`index.html`中通过`cdn`引入需要的文件
      ```
      <script src="https://cdn.bootcss.com/vue/2.5.16/vue.min.js"></script>
      <script src="https://cdn.bootcss.com/vue-router/3.0.1/vue-router.min.js"></script>
      <script src="https://unpkg.com/axios@0.18.0/dist/axios.min.js"></script>
      <script src="https://cdn.bootcss.com/jquery/3.3.1/jquery.min.js"></script>
      <script src="https://cdn.bootcss.com/echarts/4.0.4/echarts.min.js"></script>
      ```
    * 在 `build/webpack.base.conf.js` 中配置
      ```
      externals: {
        'vue': 'Vue',
        'vue-router': 'VueRouter',
        'jquery': 'jQuery',
        'axios':'axios',
        'echarts': 'echarts'
      },
      ```

2. **方法二：分包**
  * 路由按需加载
    ```
    const Weeks = () => import('../weeks/weeks')
    加载：
    {
      path: '/weeks',
      name: 'Weeks',
      component: Weeks
    },
    ```

* `Vue`工程打包部署到服务器后，静态文件（图片）不显示
  * 1.在`config`（文件夹）—>`index.js`中，添加
    ```
    build:{
      ...
      assetsPublicPathL'./',  //添加
    }
    ```

  * 2.在`build`（文件夹）—>`utils.js`添加
    ```
    if(options.extract){
      return ExtractTextPlugin.extract({
        use:loaders,
        publicPath:'../../',  //添加
        fallback:'vue-style-loader'
      })
    }else{}
    ```



##十二、Element

###1.安装与引入
>安装
```
npm i element-ui -S
```


>引入

在 main.js 中写入以下内容：
```
import Vue from 'vue';
import ElementUI from 'element-ui';
import 'element-ui/lib/theme-chalk/index.css';
import App from './App.vue';

Vue.use(ElementUI);

new Vue({
  el: '#app',
  render: h => h(App)
});
```
###2.样式覆盖

**`/deep/`**
>覆盖element默认样式
```
/deep/.el-dialog__wrapper{
}
```


###3.输入框组件

`trigger: 'blur'` 标识当是去焦点时（光标不显示的时候）触发提示

**[输入框输入限制，正则判断：](https://blog.csdn.net/redwolfchao/article/details/84973177)**
<table>
  <tr>
    <td bgcolor=yellow>
      <font color=red>`oninput`正则会导致必填项验证失效、微软输入法不能输入中文等问题，尽量改用`@input='inputFun'`方法进行输入字符判断验证</font>
    </td>
  </tr>
</table>

```
<el-input
    v-model.number="ruleForm.number"
    placeholder='请输入6位以内数字'
    maxlength="6"
    oninput="value=value.replace(/[^\d]/g,'')"
></el-input>
```

* 只能输入数字：
`oninput="value=value.replace(/[^\d]/g,'')"`

* 只能输入数字和小数点：
`oninput = "value=value.replace(/[^\d.]/g,'')"`

* 只能输入字母和汉字：
`oninput="value=value.replace(/[\d]/g,'')"`

* 只能输入字母和汉字和数字：
`oninput="value=value.replace(/[^\w\u4E00-\u9FA5]/g,'')"`

* 只能输入中文、英文、数字：
`(/^[\u4e00-\u9fa5_a-zA-Z0-9]+$/).test(value)`

###4.滚动条组件
**`<el-scrollbar></el-scrollbar>`**

<table>
  <tr>
    <td bgcolor=yellow>
      <font color=red>设置了滚动组件内部高度，会影响到组件内部滚动条高度计算，导致滚动条高度为0</font>
    </td>
  </tr>
</table>
```
<a href="javascript:void(0)" @click="AnchorLinkTo('id')">我是锚点</a>
<el-scrollbar ref="myScrollbar" style="height: 300px; width: 500px;">
  <div>
    <p>sdfsdfsd</p>
    <p>sdfsdfsd</p>
    <p>sdfsdfsd</p>
    <p ref="id">哈哈哈哈哈哈哈哈哈</p>
    <p>sdfsdfsd</p>
    <p>sdfsdfsd</p>
    <p>sdfsdfsd</p>
    <p>sdfsdfsd</p>
  </div>
</el-scrollbar>

methods: {
  AnchorLinkTo (ref) {
    this.$refs['myScrollbar'].wrap.scrollTop = this.$refs['' + ref].offsetTop
  }
}
```

```
mounted() {
  this.getList();
  //监听事件
  window.addEventListener("scroll", this.listenScrollbar, true);
},
destroyed() {
  //  删除监听事件
  window.removeEventListener("scroll", this.listenScrollbar, true);
},
methods:{
  // 监听滚动事件
    listenScrollbar: function() {
        //myScrollbar  在App.vue页面  滚动条    这个一定要找到
        let scrollTop = this.$refs['myScrollbar'].wrap.scrollTop
        if(scrollTop >= 60){
          // 出现回到顶部按钮
        }
    },
}
```

##十三、其他效果

###1.按钮边框动画
`hover`按钮时边框动画效果
```
<div class="button">按钮</div>

...

.button{
    position: relative;
    background: #3A71A8;
    border-radius: 8px;
    padding: 10px 20px;
    color: white;
    cursor: pointer;
    &:hover {
      color: #3A71A8;
      background: #fff;
      &:before,
      &:after {
        background: #3A71A8;
        width: 100%;
        transition: 600ms ease all;
      }
    }
    &:before,
    &:after {
      content: '';
      position: absolute;
      top: 0;
      right: 0;
      height: 2px;
      width: 0;
    }
    &:after {
      right: inherit;
      top: inherit;
      left: 0;
      bottom: 0;
    }
  }
```

###2.拖拽列表
**安装**
>`npm install vuedraggable`

**引入**
>`import draggable from 'vuedraggable'`

```
<template>
  <vuedraggable class="wrapper" v-model="list">
    <transition-group>
      <div v-for="item in list" :key="item" class="item">
        <p>{{item}}</p>
      </div>
    </transition-group>
  </vuedraggable>
</template>

<script>
import vuedraggable from 'vuedraggable';
export default {
  components: {vuedraggable},
  data() {
    return {
      list: [1, 2, 34, 4, 54, 5]
    };
  },
};
</script>
```