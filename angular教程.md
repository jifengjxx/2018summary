 安装步骤

1. 安装Node.js 
   在[Node.js官网](https://nodejs.org/en/download/)下载合适的版本，然后按照提示的步骤安装即可, 
   不必再去安装npm,安装Node.js时,会**自动安装npm** 
   简单的说，Node.js就是一个服务器端的JavaScript环境。NPM是随同Node.js一起安装的包管理工具，能解决Node.js代码部署上的很多问题。二者的详细介绍可参考[Node.js和NPM教程](http://www.runoob.com/nodejs/nodejs-tutorial.html)

2. 安装Typescript 
   打开终端或cmd，执行如下命令： 
   `npm install -g typescript`

3. 安装Angular-cli 
   执行如下命令： 
   `npm install -g @angular/cli` 
   angular-cli它是angular框架官方的一个构建工具，核心是webpack，以及npm做为依赖包 
   这个安装过程中可能遇到些奇怪的问题，注意事项及解决办法见文末

4. 检查版本号 
   通过检查版本号，来测试是否安装成功，执行以下命令： 
   `npm -v` 检查npm版本号 
   `tsc -v`检查typescript版本号 
   `ng -v`检查Angular版本号

5. 安装Visual Studio Code 
   VS code和我们常用的VS压根不是一回事，它只是一个开源的轻量级编辑器，而不是IDE，因为支持typescript语法，且插件功能丰富，所以选择 
   官网下载正常安装即可，接下来安装几个功能强大的**插件**： 
   Debugger for Chrome: 必需插件！！用来调试的，后边调试环节详细介绍 
   Angular 2,4 and upcoming latest TypeScript HTML Snippets: 支持Angular2.0+的特性及语法 
   Path Intellisense: 自动路径补全 
   npm Intellisense: 支持在代码中导入npm模块（require方法）时的自动补全 
   Auto Close Tag: 输入开始标签后，自动添加结束标签 
   Auto Rename Tag: 修改html标签时，自动帮你完成尾部闭合标签的同步修改 
   HTML Snippets：提供对HTML语言的支持 
   HTML CSS Support：让 html 标签上写class 智能提示当前项目所支持的样式 
   Bracket Pair Colorizer:给括号加上不同的颜色，便于匹配 
   vscode-icons：给各种文件都加上图标 
   TSLint：TS语法检测 
   beautify : 可以格式化JSON|JS|HTML|CSS|SCSS,比内置格式化好用 
   emoji:可以在代码中加表情，改善心情~

6. 创建项目 
   `ng new my-angular2-app` 
   注意这里文件名不可以包含下划线

7. 启动项目 
   进入刚刚创建的项目目录，即./my-angular2-app 
   执行命令：`ng serve`

8. 调试 
   **ng serve要先行启动**,调试是调试，不包括引导angular-cli的启动 
   点击Debug按钮，然后启动，首次会弹出调试配置，选择“Chrome”，这时正确情况下就会弹出一个新的Chrome页面； 
   VS code里可以直接打断点，查看调试中的数据信息； 
   调试时发现错误，可以直接在VS code中修改代码，保存后由于 Angular-cli 自动刷新，所以可以直接在chrome页面看到修改后的页面

   当然熟悉Chrome调试的，也可以直接用chrome的开发者工具

------

### *angular-cli安装注意事项*

此处为参考一位大神的文章，可是找不到链接了，不能挂参考链接了，如果有找的到的，麻烦告诉下我，谢谢 
angular-cli的核心是webpack，以及npm做为依赖包。但往往在安装过程中会遇到很多奇怪问题，我把这一切都追根于网络问题。 
相信很多利用npm解决依赖包的人都知道淘宝有良心产品 cnpm，但这一次cnpm在安装angular依赖包时可能会行不通。那么一个正确的安装依赖包的姿势应该是： 
1、Windows下必须是【管理员模式】下运行CMD；再使用 ng 命令。 
2、当 ng new xx 创建项目时会自动执行 npm install 下载依赖包。 
3、如果你网络没有问题的情况下，此时 ng serve 就可以正常运行。 
然，很多时候，你可能会收到像：

懵逼了吧，无从下手了吧。其实是因为所依赖的.d.ts声明文件是存在rawgit里，靠腰啊，大部分网络环境是被抢！！所以类似这种问题，建议解决你的网络问题，那就是VPN。这也是前面我说cnpm也帮不了你的原因，无意黑cnpm！ 
UPDATE 2017-04-11 有一次我尝试以下办法完成： 
npm install -g nrm 
nrm use taobao 
npm install 
当然如若不行，可以尝试以下： 
windows下使用管理员模式CMD 
1、先安装全局包 
npm uninstall -g @angular/cli 
npm cache clean 
npm install -g @angular/cli@latest 
2、创建项目 
ng new ng-article 
cd ng-article 
ng serve 
3、如果ng serve运行不起来，尝试： 
删除node_modules 
npm install 
4、依然错误 
尝试VPN，再循环第3步

升级老项目也比较简单： 
windows下使用管理员模式CMD 
1、全局版本 
npm uninstall -g @angular/cli 
npm cache clean 
npm install -g @angular/cli@latest 
2、项目版本，先删除node_modules 
npm install –save-dev @angular/cli@latest 
npm install 
3、最麻烦就是可能会一些配置的变更，这个只能看CHANGELOG.md。