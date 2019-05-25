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


一.vue cli 项目初始化
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
        


    

