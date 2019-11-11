
# 知识点累计


## css/js

    (1)	Html：  
    文档头声明 告诉浏览器以html5标准去识别页面
    (2)	标签：
 		块元素  支持宽高，独占一行，支持所有属性  div  ul  li  p dl dt dd h1-h6
        行内元素 不支持宽高，不独占一行，支持margin padding 是默认字体大小的一半  识别换行和空格  span strong  em i
        行内块 支持宽高  不独占一行   img input  select textarea 识别换行和空格 是默认字体大小一半
    (3)	默认样式：
        Ul  li  body  p  dd  dl  默认margin 8px  font-size:16px
        默认样式清除原则：用多少清多少
    (4)选择器权重：
 		!import  无穷大
        行内    1000
        id       100
        Class    10
        标签     1
        #ul1  li   100/1
        #ul  .ac   100/10
    (5)清除浮动：同级之间的浮动Clear:bothFloat:left/right
        子级和父级之间的浮动
        父级添加高度
        父级加浮动

    (6)命名规范：
            Class: --    Id: __

    (7)操作dom步骤：
    Window.onload
    获取元素
    添加事件

    (8)函数与调用：
    函数主要看调用  调用主要看返回值
    this指当前发生事件元素

    (9)箭头简写
            只有一个参数时候 小阔号可以省略
            只有返回值的时候 return 和 花括号可以省略

    (10)让不确定宽高的元素横向并垂直居中
    1. 通过position:absolute给当前图片设置
    Left:0;  top:0; 
    right:0;  bottom:0;
    2. 通过margin：auto给当前图片设置并给html和body设置高度
    Hright: 100%;
    Width: 100%;
    3. 通过-webkit-box来给元素的父元素设置
    Html ---- overflow: hidden;
    Display: -webkit-box;
    -webkit-box-align: center;
    -webkit-box-pack: center;
    4. 通过display：flex；主要元素来给父元素设置
    Html ---- overflow: hidden;
    Display:flex;
    Justify-content: center;
    Align-item: center;
    5. 通过display:table-cell 来给body和父元素设置
    Body{ display:table }
    Display: table-cell;
    Text-align: center;
    Vertical-align: middle;



## css/基础/vue

    (1)匈牙利命名：
    类型前缀+驼峰命名
    类型前缀：
    O => 一个  object(对象)
    A => 一组  array（数组）
    B => 布尔值  boolean
    I => 整数  integer
    S => 字符串  string
    F => 浮点数  float
            Fn => 函数  function
    Re => 正则  regexp
    V => 变体变量 variant
    驼峰命名：
    document.getElementById
    oDiv  aLi

    (2)前后端/联调：
    前后端分离
    前端多 
    页面上的主要的功能 （页面跳转、搜索、筛选..）
    后端少 
    数据库的搭建（接口、后端框架搭建、后端数据库搭建..）
    劣势 ：不利于前后端的配合以及联调
    前后端不分离
    前端少
    主要负责切页面、写效果
    一个前端对多个后端
    后端多
    核心功能开发、后台模板、数据渲染
    Node、jade、ejs
    联调：
    前后端做项目  数据是假数据
    将假数据变成线上真实数据的过程

    （3）公司包含：
    技术：
    前端  后端  ui设计师  测试  产品
    运维  推广  seo
    人数/名字

    （4）mvc/mvp/mvvm
    M:数据   v:页面  c/p/vm:业务逻辑
    其实，前端没有这种mvc mvvm这种思想 mvc 这种思想主要是从后端借鉴过来,m就是我们数据 v指的就是页面 c就是指的业务逻辑
            从页面这端触发，告诉c这一层(业务逻辑) 让c这一层从后台接口获取数据 并且把数据直接返回给v这一层 但是这种模式下会有两个突出问题
            耦合度太高(牵一发而动全身个，修改一处所有地方有可能都需要进行修改) c这一端过于庞大 这就是传统mvc问题 ！最近出来新的思想
            叫 mvp  m还是数据 v页面 p指的是业务逻辑 看似和mvc一样 但还是有些区别  页面触发 直接从p这一端要数据 并且p这一端 会把数据
            返回给v一层  所以会降低一部分的耦合度 但实际上 p这一端还是过于庞大 所以我们出来一种叫做mvvm这种思路下 都把他们划分为一个一个小组件
            虽然  m和v之间会有这种关联，但是因为都已经拆分为组件，所以说业务逻辑 耦合度都不会 过高 过大

    （5）前后端渲染：
    前端渲染
    用户体验好、传输数据量小
    Vue  ajks
    后端渲染
    安全、利于SEO优化、性能高
    Ejs

    （6）npm/cnpm:
    Npm
    国外 速度慢 效率变低
    开发中间件(插件)
    Cnpm
    国内 速度快 效果高
    每隔十分钟会将npm内容同步到cnpm

    （7）依赖项：
    Dependencies     -S
    生产依赖项-----项目上线依赖的模块
    devDependencies  -D
    开发依赖项-----清场开发需要依赖项目

    （8）meta比例：
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
            name="viewport"     设置分辨率   
            width=device-width  屏幕多大分辨率就设置多大  屏幕越大分辨率越大
            initial-scale=1.0,  初始化缩放比例
            maximum-scale=1.0,  最大缩放比例
            user-scalable=0     禁止用户缩放

    （9）scoped：
    在vue中style样式
    Scoped  在当前的.Vue文件生效
    没有scoped  代表全局样式

    （10）{{ 数据名 }}
    Vue表达式  输出数据
    {{ }} ----- 转义输出 不会解析标签
    v-html ---- 原义标签  会解析标签


## vue/复习
 
    （1）vue的下载打包
    下载所有项目依赖：  cnpm i
    启动项目：   npm run dev
    打包项目：   npm run build

    （2）指令：
    V-show: 显示/隐藏   始终渲染并保持在dom中
    v-if： 添加/删除		根据表达式的值的真假
    V-bind: 属性上绑定数据 /:
    V-on: 绑定事件 /@	用于监听dom事件
    v-for： 循环遍历对象		优先级高于v-if和v-show
    V-model: 创建数据双向绑定
    v-html： 将数据解释为纯文本为了输出真正的html

    V-show一般会用在切换比较频繁   v-if切换不频繁的
    Key： 渲染数据时每条数据唯一标识

    （3）组件：
    组件就是指功能性的标签
    一切都是组件  一切都是数据

    （4）移动端框架(vant)
    下载指令：Cnpm  i  vant  -S

    全局引入：（main.js）
    import Vant from 'vant';
        import 'vant/lib/index.css';
        Vue.use(Vant);

    栅格布局：  24列
    Ui框架：
    Swipe  轮播图
    Button  按钮
    icon   图标
    Layout  布局
    Search  输入框

    （5）什么是vue
        是一套构建用户界面的渐进式框架，采用自底向上增量开发的设计，完全有能力驱动采用单文件组件和vue生态系统支持的库开发的复杂单页面应用

    （6）vue的优点：
    两个核心点：响应式  组件
    其他优点：易用
            虚拟DOM
            双向数据绑定
            体积小
            生态圈繁荣、学习成本低


## 路由/高级动画

    （1）什么是路由
    根据不同地址，访问对应页面
    {
        path: '/surprised',     访问路径
        name: 'surprised',      模块名字
        component: surprised    访问地址时对应组件
    }

    （2）router-link
    类似于a标签
    To 跳转地址：	<router-link to='/'>首页</router-link>
    数据传值：
    Query：
    <router-link :to="{path:'/login',query:{name:id}}">登录</router-link>
    接收数据： this.$route.query.name
    Params：
    <router-link :to="'/car/'+id">购物车</router-link>
    接收数据：  this.$route.params.id

    （3）高级动画：
    https://wqs.jd.com/promote/2015/mum/index.html?ptag=17005.2.9&from=timeline&isappinstalled=0
    Css3专用练习：
    帧数：
    @-webkit-keyframes child {
            0% { background-position: 0 calc(-140px * 0); }
            20% { background-position: 0 calc(-140px * 1); }
            40% { background-position: 0 calc(-140px * 2); }
            60% { background-position: 0 calc(-140px * 3); }
            80% { background-position: 0 calc(-140px * 4); }
            100% { background-position: 0 calc(-140px * 5); }
        }
    添加动画：
    动画名    执行一次时间    走几步      无限循环
    animation: action2     .3s           steps(1)     infinite;

    （4）Element ui使用：
    下载：  cnpm  i  element-ui  -S
    引用在main.js里

    10-28：路由/拆分组件

    （1）组件的特性：
    便于协同开发   	方便复用 	提升整个项目的可维护性
    可定制		高聚合		低耦合
    互操作性 - 多组件互相协同

    （2）组件的基本构成：
    样式结构
    行为逻辑
    数据

    （3）拆分组件
    * 根据页面拆分组件，根据需求在页面内引入
    import comnav from './components/nav/com-nav';	  //路径
    * 并在当前页面引用components方法告诉vue这是我要使用的组件
    components:{
    comnav
    },
    * 在父级div中写入组件名称 / 和标签一样
    <comnav></comnav>

    （4）动态组件：
    多个组件可以使用同一个挂载点，动态切换
    ----- 在router/index里引用并定义路由跳转方向：
    在配置项里可自定义属性名字
    import home from '@/components/home/home'
    routes: [ 
    {
    path: '/',
    name: 'home',
    component: home,
    //可自定义属性名
    tit:'首页',
    hidden:true,
    iconCl:'wap-home-o',
    },

    ----- 在组件页面定义并引入路由属性
    data(){
    return {   //自定义名接收路由传过来的数据
    route:this.$router.options.routes
    }
    },

    ----- 可以用vue的生命周期查看是否引入
    mounted(){
    console.log(this.route)
    },

    ----- 在父级div中使用v-for渲染出路由内容
    <router-link 
    :to='item.path'   // 跳转的路径
    :key='index'      
            v-if='item.hidden'  // if判断路由里的true和false 	  
    v-for='(item,index) in route' // 循环当前路由获取内容
    >
    <span>{{item.tit}}</span>	    //内容渲染
    <van-icon size='24' :name="item.iconCl" info="1" />
    </router-link>

    （5）二级路由
    在当前页面跳转不刷新页面
    在路由配置里给一级路由内添加children属性并定义跳转
    export default new Router({
    routes: [ 
    {
    path: '/',
    name: 'home',
    component: home,
    tit:'首页',
    hidden:true,
    iconCl:'wap-home-o',
    children:[     //二级路由内容
    {
    path: '/follow',
    name: 'follow',
    component: follow,
    tit:'关注',
    hidden:true,
    iconCl:'label-o'
    }
    ],
    },

    需要注意：在当前组件引用后需要写入路由视图
    <router-link to='/follow'>关注</router-link>  //引用
    <router-view></router-view>			//配置路由视图

    （6）引用样式css / js：
    列：css
    * 自定义css文件夹写入样式
    列：【 nav.css / det.css / header.css 】

    * 创建单独的css文件接收其他样式（使用@import）
    列：【 all.css 】
    //引入所有样式在当前文件夹
    @import './header.css';
    @import './nav.css';
    @import './det.css'

    * 在全局内引入（main.js）
    import './assets/css/all.css'   //assets文件下css文件夹下的all.css

    列：js
    多个方法引入：
    import {sum,max} from '../js/common'
    返回多个方法：
    export const sum=(a,b)=>{return a+b;}
    export const max=(item)=>{return Math.max.apply(null,item);}

    （7）vue路由模式：
    一共三种模式：hash / history / abstract  常用前两种
    Mode : 
    类型：string
    默认值：hash（浏览器环境） | abstract（node.Js 环境）
    可选值：hash / history / abstract
    配置路由模式：
    Hash： 使用url hash值来做路由，支持所有浏览器
    History:  依赖html5 history API和服务器配置
    Abstract：支持所有javascript运行模式，如node.js服务器端，如果发现			 没有浏览器的API，路由会强制自动进入这个模式
    （8）重定向：
    Redirect：自定义首次显示的页面
    可以通过routes配置来完成
    Const router = new vuerouter({
    Routes: [
    {path: ‘/a’ , redirect: ‘/b’ }
    ]
    })
    重定向的目标也可以是一个命名的路由
    Const router = new vuerouter({
    Routes: [
    {path: ‘/a’ , redirect: { name: ‘foo’ } }
    ]
    })
    甚至一个方法，动态返回重定向目标
    Const router = new vuerouter({
    Routes: [
    {path: ‘/a’ , redirect: to => { 
    //方法接收  目标路由  作为参数
    //return  重定向的字符串路径 / 路径对象
    }}
    ]
    })

    10-29：组件传值/生命周期
    （1）传参及对比
    可以用this.$router.push( ) 进行传值
    Query：
    this.$router.push({path:'/':query:{a:12}})
            name
            path
    接收：  this.$route.query.a
    特性：	 刷新后数据还在	
            地址栏进行传递
    不安全
    接收参数不一样
    Params：
    this.$router.push({path:'/':params:{a:12}})
            Name
    接收：   this.$route.params.a
    特性：	  刷新后数据不存在
    类似于post
    接收参数不一样

    （2）$route和$router 对比
    $route
    是$router一部分配置信息
    $router
    是整个路由信息

    （3）传值方法
    @ 父传子
    父级故意暴露给子级
    父级：
    <div class="com">
        <child :money='msg'></child>
    </div>
    子级：//props方法
    props:{
        money:String
    },
    子级接收：
    This.money

    @ 子传父
    子级传递数值给父级
    子级：
    用this.$emit(‘名字’，数据) 发射传递
    父级：
    <div class="com">
        <child :money='msg' @send='fn'></child>
    </div>
    //方法
    methods:{
        fn(item){
            console.log(item);
            }
        }

    @ 同级之间传递
    Car组件 传递给 parent组件
    Car:
    <input type="button" value="发射给parent" @click='fnSend()'>
    //方法接收
    methods:{
        fnSend(){
            this.bus.$emit('sendmsg',this.msg)
            }
    }
    Parent：
    //接收传值
    this.bus.$on('sendmsg',(item)=>{
            this.msg=item;
    })

    （4）进阶子传父
    父级
    <div class="parent">
        <child :to-send='obj'></child>	  //把数据故意暴露给子级
        {{obj.a}}  	//展示子级的传递过来数据
    </div>
        //当前页面数据里面定义的值
    data () {
        return {
            msg: 'parent',
            obj:{
                a:12
            }
            }
        }
    子级
    //接收父组件暴露的值
    props:{
        toSend:Object
    },
    //通过点击事件触发
    <input type="button" value='传递到父级' @click='fnChange()'> 
    //通过方法来改变
    methods:{
        fnChange(){
    //方法
            this.toSend.a=5;
        }
        },

    （5）vue中的生命周期
    @Vue2.0默认有 八 个生命周期
    @一共有 十二 个：
    1.Creating状态/创建：
    'beforeCreate',	//实例创建之前调用
    'created',			//实例创建成功，data数据显示
    2.Mounting状态/挂载：
    'beforeMount',	//数据中的data在模板先占一个位置
    'mounted',		//模板中的data数据直接显示出来
    3.updating状态/更新：
    'beforeUpdate',	//当data数据发生变化调用发生在虚拟dom之前
    'updated',		//数据更改导致虚拟dom重新渲染和打补丁
    4.destroying状态/销毁：
    'beforeDestroy',	//在vue实例销毁之前调用 /实例仍然可用
    'destroyed',		//在vue实例销毁之后调用 /全部销毁
    5.使用keep--alive状态：
    'activated',		//用来缓存组件状态，created钩子不会重复调用
    'deactivated',		//组件移除时触发
    6.v2.5+新状态
    'errorCaptured',	//错误处理机制 当捕获到子孙组件的错误时被调用，会收到三个参数：错误对象/发生错误的实例/错误信息来源的字符串  可以返回false以阻止错误继续向上传播
    'serverPrefetch'	//前身是ssrprefetch，允许在渲染过程中等待异步数据，可以在任何组件中使用  v2.6.10版本后有

    @生命周期在vue中的用法：
    beforeCreate( ){
    console.log('数据 方法 页面 渲染之前')
    },
    created( ){
    console.log('创建完成之后 数据方法 都加载完成 页面结构还没有加载完成');
    },
    beforeMount( ){
    console.log('页面结构加载之前 结构已经准备 但数据和方法已经是加载完成');
    },
    mounted( ){
    console.log('页面结构已经渲染完成 ,数据和方法已经是加载完成');
    },
    beforeUpdate( ){
    console.log('数据已经最新的但是页面上还没有跟新过来')
    },
    updated( ){
    console.log('数据跟新过来 页面上也跟新完成')
    },
    beforeDestroy( ){
    console.log('销毁之前');
    },
    destroyed( ){
    console.log('之后')
    }

    （6）什么是keep-alive
    *是vue内置的一个组件，可以使被包含的组件保留状态，或避免重新渲染。
    *自身不会渲染一个dom元素，也不会出现在父组件中。
    *是vue源码中实现的一个全局抽象组件，通过自定义render函数并利用了插槽来	实现数据的缓存与更新。
    *在vue2.1.0版本后新加入两个属性：
    Include(包含的组件缓存)
    Exclude(排除的组件不缓存，优先级大于include)

    （7）自定义指令
    *基础：
    可以给指令指定一个优先级（默认是 1000）
    除了内置指令，自定义指令提供一种机制将数据的变化映射为 DOM 行为
    可以用 Vue.directive(id, definition) 方法注册一个全局自定义指令，它接收两个参数指令 ID 与定义对象
    也可以用组件的 directives 选项注册一个局部自定义指令。

    *钩子函数：
    定义对象可以提供自选钩子函数
    bind：只调用一次，在指令第一次绑定到元素上时调用。
    update： 在 bind 之后立即以初始值为参数第一次调用，之后每当绑定值变化时调用，参数为新值与旧值。
    unbind：只调用一次，在指令从元素上解绑时调用。
    inserted: 被绑定元素插入父节点时调用
    componentupdated： 所在组件的虚拟节点及子节点全部更新后调用

    钩子函数的参数：【el,binding,vnode 和 oldVnode】
    el：指令所绑定的元素，可以用来直接操作 DOM 。
    binding：一个对象，包含以下属性：
    name：指令名，不包括 v- 前缀。
    value：指令的绑定值，例如：v-my-directive="1 + 1" 中，绑定值为 2。
    oldValue：指令绑定的前一个值，仅在 update 和 componentUpdated 钩子中可用。无论值是否改变都可用。
    expression：字符串形式的指令表达式。例如 v-my-directive="1 + 1" 中，表达式为 "1 + 1"。
    arg：传给指令的参数，可选。例如 v-my-directive:foo 中，参数为 "foo"。
    modifiers：一个包含修饰符的对象。例如：v-my-directive.foo.bar 中，修饰符对象为 { foo: true, bar: true }。
    vnode：Vue 编译生成的虚拟节点。移步 VNode API 来了解更多详情。
    oldVnode：上一个虚拟节点，仅在 update 和 componentUpdated 钩子中可用。

    *示例：
        Vue.directive("smallfour",{
    //被绑定
            bind:function(el,binding){	
                console.log('1 - bind');
            },
    //绑定到节点
            inserted: function () {		
                console.log('2 - inserted');
            },
            //组件更新
    update: function () {		
                console.log('3 - update');
            },
    //组件更新完成
            componentUpdated: function () {		
                console.log('4 - componentUpdated');
            },
    //解绑
            unbind: function () {		
                console.log('5 - unbind');
            }
        });

    ***********************************
    箭头函数和普通函数
        axios获取数据的时候 用箭头函数能够获取data数据用普通函数获取不到
        原因：this指向不同
        解决办法：使用箭头函数
    外部引入js方法，不能直接在HTML里面使用
        解决方法：在methods里面定义一个方法 引入外部js	

    弹框方法
        confirm('你确定删除吗')

    Vue写服务器数据
    1）配置跨域请求  在config下index.js配置
    proxyTable: {
    '/api/**': {
    // target: 'http://192.168.43.26:81/car',//后端接口地址
    target: 'http://172.16.89.27:81/',//后端接口地址
    changeOrigin: true,//是否允许跨越
    pathRewrite: {
    '^/api': '/',//重写,
    }
    }
    },

    2）Src创建api / common文件夹
    Api：封装/服务器路径/引入axios
    import axios from 'axios';
    //可写入多个路径
    export const Lyb = params =>{
    return axios.get(`api/myWish/wish.php`,{params:params})}

    Common：封装组件/解析数据/定义方法
    let obj = {
    //定义解析数据
    toEval: function(s){
    return eval(`(${s})`)
    },
    }
    export default obj;

    3）在vue组件中引入
    //引入css样式
    import "./Css/index.css";
    //引入js接口文件  可引用多个名称
    import { Lyb } from "./../api/api";
    //引入方法
    import common from './../common/js/common';

    4）axios使用 列：
    //获取所有心愿
    fnGet(){
    let obj = {
    act: 'get', //接口方法
    }
    Lyb(obj).then(res => {
    let arr = common.toEval(res.data);
    //push到list数组里
    this.list = arr.msg
    console.log(this.list)
    })
    },

    使用生命周期渲染
    mounted() {
    //获取所有心愿
    this.fnGet()
    },
    生命周期使用 列：
    //点击添加事件
    fnAdd(){
    let obj = {
    act: 'add', // 接口方法
    username: this.txt, //input内容
    content: this.cont //文本域内容
    }
    Lyb(obj).then(res => {
    let s1 = common.toEval(res.data)
    this.fnGet() //重新获取数据
    console.log(s1)
    })
    },


    *************
    1）服务器时间用法 / 可在common文件内使用
    //补零方法**** 小于10补零
    toDou: function (n) {
    return n < 10 ? '0' + n : '' + n;
    },
    //自定义方法来转换时间格式
    //方法不能直接导入到循环中，需要用methods方法接收定义
    toTime: function (t) {
    var oDate = new Date();
    oDate.setTime(t * 1000);
    var iY = obj.toDou(oDate.getFullYear()); //年
    var iM = obj.toDou(oDate.getMonth()+1); //月
    var iD = obj.toDou(oDate.getDate()); //日

    var iH = obj.toDou(oDate.getHours()); //时
    var iMin = obj.toDou(oDate.getMinutes()); //分
    var iS = obj.toDou(oDate.getSeconds()); //秒

    return `${iY}-${iM}-${iD} ${iH}:${iMin}:${iS}`
    }
    在组件中使用methods接收
    // 引入时间方法转换
    changeT(t){
    return common.toTime(t)
    },
    2）自定义指令 列：
    * 在需要位置绑定指令
    <!-- 自定义指令 拖拽/ 随机颜色/ 随机位置 -->
    <dl v-hello:{drag:0,rndBg:0,rndPos:0} class='paper a1' v-for="(item,index) in list" :key="index">

    * 在mian.js里引用封装的方法
    import common from './common/js/common'

    * common里定义封装的方法
    //封装自定义方法 /随机数
    rnd:function(n,m){
    return parseInt(Math.random()*(m-n)+n);
    },
    zIndex:1, //给心愿卡添加基础
    getC:function(obj){
    return {
    w:document.documentElement.clientWidth-obj.offsetWidth,
    h:document.documentElement.clientHeight-obj.offsetHeight-126 
    }
    }

    * 全局内写入
    //自定义指令 随机位置，随机颜色，拖拽
    Vue.directive('hello',{
    inserted:function(el,binding,vnode){
    let arg = common.toEval(binding.arg);
    var w = common.getC(el).w;
    var h = common.getC(el).h;
    //随机位置 为true时随机 不为0时不随机
    if(!arg.rndPos){
    el.style.left = common.rnd(0,w)+'px';
    el.style.top = common.rnd(0,h)+'px';
    }
    //随机颜色
    if(!arg.rndBg){
    el.className = `paper a${common.rnd(1,6)}`;
    }

    * 拖拽
    if(!arg.drag){
    //鼠标按下事件
    el.onmousedown = function(ev){
    el.style.zIndex = common.zIndex++
    var oEvent = ev||event;
    var disX = oEvent.clientX-el.offsetLeft;
    var disY = oEvent.clientY-el.offsetTop;
    //鼠标移动事件
    document.onmousemove = function(ev){
    var oEvent = ev||event;
    var l = oEvent.clientX-disX;
    var t = oEvent.clientY-disY;
    el.style.left = l+'px';
    el.style.top = t+'px';
    }
    //鼠标抬起事件
    document.onmouseup = function(){
    document.onmousemove = null;
    document.onmouseup = null;
    }
    return false;
    }
    }
    （3）模仿服务器数据
    Mock
    http://mockjs.com/

    （4）axios 数据拦截
    https://blog.csdn.net/qq_42750608/article/details/91850919

    （5）axios并发请求
    Axios.All（[ ,]）返回的结果是一个数组
    使用axios.Spread可将数组展开

    （6）cookie的使用
    cookie定义：
    Cookie存储时间是一个会话，从浏览器打开之后到浏览器关闭之前
    缓存：
    浏览器对相同的地址只会请求一次
    Cookie：
    a)必须是服务器环境
        b)有过期时间
        c)不安全
        d)不能跨浏览器
        e)默认路径是当前文件夹

    使用：
    Cookie设置：
                document.cookie='名字=值'
    获取：
    function getCookie(name){
            var arr=document.cookie.split('; ');
                for(var i=0;i<arr.length;i++){
                    var Arr=arr[i].split('=');
                    if(name==Arr[0]){
                        return Arr[1];
                    }
                }
                }
    添加：
    function setCookie(name,value,iDay){
            var oDate=new Date();
            oDate.setDate(oDate.getDate()+iDay);
            document.cookie=`${name}=${value};expires=${oDate};path=/`;
    }
    删除：
    function delCookie(name){
            setCookie(name,'ccc',-3)
        }


    Vuex：
    官网：https://vuex.vuejs.org/zh/
    了解：https://my.oschina.net/wangnian/blog/2055631
    （1）什么是vuex
    是一个专门为vue.js应用程序开发的状态管理模式	

    （2）vue有什么好处及应用场景
    好处：
    可以做状态管理
    采用localstoreage保存信息
    数据一致存储在用户的客户端中
    使用场景：
    登录信息
    购物车
    复杂的组件通信

    （3）vue的核心概念
    State    状态 
    Getter   计算属性
    Mutation 改变状态
    Action   异步操作
    Module   模块

    （4）vuex常用的方法
    Dispatch 		actions   		commit
    Mutations  	state   		strict
    Getters  		mapGetters 	mapActions
    （5）vuex的使用：
    指令：cnpm install vuex -S

    (1)在src文件夹中创建vuex/store.js文件并在全局引入
    import store from './vuex/store'
    并在实例化中写入
    new Vue({
    el: '#app',
    router,
    store,
    components: { App },
    template: '<App/>'
    })


    （2）在store中引入
    import Vue from 'vue'
    import Vuex from 'vuex'

    Vue.use(Vuex)

    const store = new Vuex.Store({
    // 状态管理对象
    state: {
    lists:[]
    },
    // mutations
    mutations: {

    }
    })
    export default store
    多文件引入：
    import Vue from 'vue'
    import VueX from 'vuex'
    // *as 获取当前文件所有元素
    import * as actions from './actions';
    import * as mutations from './mutations';
    import * as getters from './getters';

    Vue.use(VueX);
    //定义状态管理
    const state={
    list:[12,5],
    };
    export default new VueX.Store({  //导出vuex
    strict:true,
    state,
    mutations,
    actions,
    getters
    });

    （3）在多组件里应用：
    Actions.js里
    Actions 告诉 mutation 里面的方法执行（修改数据）
    Commit（‘方法名’，传递数据）
    //哪里需要引用哪里
    import com from './../common/js/common';
    import { weibo } from './../api/api';
    // 告诉mutation 里面的方法执行 请求数据再去定义

    // 封装获取获取页码 方便使用
    export const loadPagination = async ({commit},arg) => {
    commit('setPagination',arr)
    };

    Mutations.js里
    Mutations(修改数据)
    // 执行actions传过来的方法（修改数据） 去getters定义

    //获取页码
    export const setPagination = (state,arg)=>{
    state.pagination = arg;
    };

    Getters.js里
    Getters
    返回当前想要数据，函数当前的数据
    // 获取state 返回当前想要的数据 去页面触发

    //返回store中的数据
    //获取页码
    export const getPagination = state=>{
    return state.pagination;
    };

    Vue文件里：
    用到什么就引用什么
    import {mapActions} from 'vuex';  所有请求拿过来
    import {mapGetters} from 'vuex';  所有的state数据拿过来

    Methods里面定义
    methods: {
            //调取方法名
    ...mapActions([
                    'loadPagination',
                    'loadOneData'
            ]),

    Components里应用
    computed: {
    //使用对象展开运算符 getters混入 computed对象中
    ...mapGetters([
        'getPageMsg', //在getters里面 state 数据值
        'getPagination', 
    ])
    },

    生命周期应用
    async mounted() {
    //提交的时候获取页码
    await this.loadPagination();
    },


    Git方法：
    （1）什么是git
    Git是一个免费，开源的版本控制软件

    （2）什么是版本控制系统
    本控制是一种记录一个或若干个文件内容变化，以便将来查阅特定版本修订情况得系统。

    （3）使用git（码云）
    A)	注册，右上角创建私有仓库

    B)	git提交内容
    安装：
    Git线上地址：https://git-scm.com/
    下载 64-bit Git for Windows Setup.
    验证：
    是否安装成功：
    空白文件夹单击右键出现
    Git GUI here
    Git Bash here
    安装成功
    使用：
    Git命令进入文件夹，将仓库的东西获取过来
    1)Git init 将文件夹初始化为git仓库
    2)先将仓库clone到本地，修改后push到码云仓库
    Git clone ‘仓库文件链接’
    列：git clone https://gitee.com/judy66/storehouse.git
    命令行中指令：
    退出：cd..
    进入文件夹： cd
    查看文件夹有那些文件： dir / is
    清屏： clear
    Git指令提交步骤：
    1) Git init   初始化为仓库
    2) Git clone https地址    克隆仓库里面的内容
    3) 身份验证（只有第一次才会记录消息）
    4) Git config --global user.name ‘名字’
    5) Git config --global user.email ‘邮箱’
    6) Git status    查看有多少内容准备提交
    7) Git add -A    全部提交
    Git add a.html  单独提交
    8) Git commit -m   记录当前信息
    9) Git push https地址 master   提交（指定到哪个仓库）
    配置公钥：
    先初始化为git仓库 
    git init
    配置地址：
    https://gitee.com/help/articles/4181
    如果没有配置，访问ssh会报错
    生成一个公钥：
    ssh-keygen -t rsa -C "地址/邮箱"
    查看公钥：
    cat ~/.ssh/id_rsa.pub
    对比：
    当时用ssh地址获取项目
    Ssh比https 更安全，传输量大
    冲突处理：
    没冲突时
    1）git init
    2）Git status
    3）Git add .
    4）Git commit -m ‘项目提交’
    5）Git pull ssh地址 master
    6）Git push ssh地址 master
    有冲突时
    1）git init
    2）Git status
    3）Git add .
    4）Git commit -m ‘项目提交’
    5）git pull ssh地址 master   有冲突协商解决，留一份
    6）git status  查看状态
    7) git add . 
    8）git commit -m ‘项目提交’
    版本撤回：
    Git可以做项目的版本管理
    网址：https://gitee.com/help/articles/4195
    命令行： Get log
    更换： git reset --hard 版本号
    创建分支：
    创建：
    Git branch 分支名
    查看分支：
    Git branch
    切换分支：
    Git checkout 分支名
    提交项目和分支：
    Git push 地址 分支名/项目名







