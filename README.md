使用git上传项目到github步骤：
1.首先在github上新建仓库名字tangjinzhou
2.git clone https://github.com/yousi2016/tangjinzhou.git到指定文件夹，这样tangjinzhou文件夹就会受到git控制了
3.Administrator@PC-20180723OWWX MINGW64 /d/geekbang/tangjinzhou (master)
4.新创建两个本地存储库github和gitee
    Administrator@PC-20180723OWWX MINGW64 /d/geekbang/tangjinzhou (master)
    $ git remote add github git@github.com:yousi2016/tangjinzhou.git

    Administrator@PC-20180723OWWX MINGW64 /d/geekbang/tangjinzhou (master)
    $ git remote add gitee git@gitee.com:frontEndArchitect/tangjinzhou.git
5.删掉以前的origin存储库 $ git remote rm origin
    Administrator@PC-20180723OWWX MINGW64 /d/geekbang/tangjinzhou (master)
    $ git remote -v
    gitee   git@gitee.com:frontEndArchitect/tangjinzhou.git (fetch)
    gitee   git@gitee.com:frontEndArchitect/tangjinzhou.git (push)
    github  git@github.com:yousi2016/tangjinzhou.git (fetch)
    github  git@github.com:yousi2016/tangjinzhou.git (push)
    origin  https://github.com/yousi2016/tangjinzhou.git (fetch)
    origin  https://github.com/yousi2016/tangjinzhou.git (push)

    Administrator@PC-20180723OWWX MINGW64 /d/geekbang/tangjinzhou (master)
    $ git remote rm origin

    Administrator@PC-20180723OWWX MINGW64 /d/geekbang/tangjinzhou (master)
    $ git remote -v
    gitee   git@gitee.com:frontEndArchitect/tangjinzhou.git (fetch)
    gitee   git@gitee.com:frontEndArchitect/tangjinzhou.git (push)
    github  git@github.com:yousi2016/tangjinzhou.git (fetch)
    github  git@github.com:yousi2016/tangjinzhou.git (push)
6.$ git push github master
    Counting objects: 3, done.
    Delta compression using up to 4 threads.
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 2.40 KiB | 0 bytes/s, done.
    Total 3 (delta 0), reused 0 (delta 0)
    To git@github.com:yousi2016/tangjinzhou.git
    65b6343..cda1f4e  master -> master
7.在gitee上导入github仓库tangjinzhou即可







vue2.5/vue-cli3.0版本更新引发的一些常见问题:
https://segmentfault.com/a/1190000014219426?utm_source=channel-hottest

在Windows下用命令行升级NodeJS和npm的版本
国人写的gnvm：http://ksria.com/gnvm/
https://www.jianshu.com/p/801d84f1d773?utm_campaign

https://www.npmjs.com.cn/
安装指定版本nodejs：gnvm install 10.15.3

Nodejs安装及环境配置
https://www.jianshu.com/p/13f45e24b1de



05 | 初识单文件组件
    vue cli 项目初始化
    1.npm install -g @vue/cli
    2.vue create my-app
        1.选择默认的default即可按回车生成项目目录和依赖脚本
        2.一路按回车就行，等待一段时间后会出现以下信息
            ? Please pick a preset: Manually select features
            ? Check the features needed for your project: (Press <space> to select, <a> to t
            ? Check the features needed for your project: (Press <space> to select, <a> to t
            ? Pick a linter / formatter config: (Use arrow keys)
            ? Pick a linter / formatter config: Basic
            ? Pick additional lint features: (Press <space> to select, <a> to toggle all, <i
            ? Pick additional lint features: (Press <space> to select, <a> to toggle all, <i
            ? Where do you prefer placing config for Babel, PostCSS, ESLint, etc.? (Use arro
            ? Where do you prefer placing config for Babel, PostCSS, ESLint, etc.? In dedica
            ? Save this as a preset for future projects? (y/N)
            ? Save this as a preset for future projects? No
            -  Creating project in D:\geekbang\tangjinzhou\my-app.
            ✨  Creating project in D:\geekbang\tangjinzhou\my-app.
            -  Initializing git repository...
            🗃  Initializing git repository...
            ⚙  Installing CLI plugins. This might take a while...



            > yorkie@2.0.0 install D:\geekbang\tangjinzhou\my-app\node_modules\yorkie
            > node bin/install.js

            setting up Git hooks
            done


            > core-js@2.6.8 postinstall D:\geekbang\tangjinzhou\my-app\node_modules\core-js
            > node -e "try { require('./scripts/postinstall'); } catch (e) { /* empty */ }"

            added 1155 packages from 914 contributors and audited 23635 packages in 231.824s
            found 0 vulnerabilities

            🚀  Invoking generators...
            📦  Installing additional dependencies...

            added 36 packages from 27 contributors, updated 2 packages, moved 9 packages and audited 23924 packages in 53.19s
            found 0 vulnerabilities

            -  Running completion hooks...
            ⚓  Running completion hooks...

            -  Generating README.md...
            📄  Generating README.md...

            🎉  Successfully created project my-app.
            👉  Get started with the following commands:

            $ cd my-app
            $ npm run serve

    3.cd my-app
    4.npm run serve
        如果出现以下信息说明运行成功
        > my-app@0.1.0 serve D:\geekbang\tangjinzhou\my-app
  
    
    5.进入http://localhost:8080/
    6.将second.html里面的html，css， js复制到App.vue里面然后处理报错即可
    7.在components下新建一个Todoitem.vue
        <template>
            <li class="item">{{item}}</li>
        </template>

        <script>
        export default {
            //给标签自定义属性item
            props:['item'],
        }
        </script>

        <style>
            /*样式也是全局的 */
            .item{
                color: green;
            }
        </style>
    8.在App.vue中使用Todoitem.vue就得引入
        //引入组件TodouItem.vue
        import TodouItem from "./components/TodoItem";
        注册组件：
            components: {
                TodouItem
            }
        vs code格式化代码的快捷键 Shift + Alt + F
        最后将脚手架生成的自带样式干掉
        #app {
            font-family: "Avenir", Helvetica, Arial, sans-serif;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            text-align: center;
            color: #2c3e50;
            margin-top: 60px;
        }
        使用插槽
        <todo-item v-for="item in list" :key="item" :item="item">
          <span style="font-size:20px;">{{item}}</span>
        </todo-item>
        扩展功能
06 | Vue组件的核心概念(1)：属性
    组件概念：小型的，独立的，可以复用的，ui模块
    组件三大核心概念：属性，事件，插槽
    vue组件=vue实例=new Vue(options),以后90%的工作都是围绕配置options进行的哦
    属性：
        自定义属性props:组件props中声明的属性

        原生属性attrs：没有声明的属性，默认自动挂在到组件根元素上，设置inheritAttrs为false可以关闭自动挂载

        特殊属性class,style：挂载到组件根元素上，支持字符串，对象，数组等多种语法

07 | Vue组件的核心概念(2)：事件   
    事件
        普通事件
            @click，@input，@change，@xxx等事件，
            通过this.$emit('xxx', ...)触发
        修饰符事件
            @input.trim, @click.stop,@submit.prevent等，一般用于原生HTML元素，自定义组件需要自行开发支持

08 | Vue组件的核心概念(3)：插槽
        普通插槽
            <template slot='xxx'>...</template>
            <template v-slot:xxx>...</template>
        作用域插槽
            <template slot='xxx' slot-scope='props'>...</template>
            <template v-slot:xxx='props'>...</template>

09 | 双向绑定和单向数据流不冲突
    双向绑定：
        model更新view
        view更新model
    单向数据流
        model更新view
    
    vue是单向数据流，不是双向绑定
    vue的双向绑定不过是语法糖
    object.definedProperty是用来做响应式更新的，和双向绑定没关系

10 | 理解虚拟DOM及key属性的作用

11 | 如何触发组件的更新
    任何直接操作dom的行为都是在作死
    
    

    


        


    

