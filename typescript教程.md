什么是 TypeScript？

TypeScript 是一种由微软开发的自由和开源的编程语言，它是JavaScript的一个超集，扩展了JavaScript的语法。

语法特性

类 Classes

接口 Interfaces

模块 Modules

类型注解 Type annotations

编译时类型检查 Compile time type checking

Arrow 函数 (类似 C# 的 Lambda 表达式)

JavaScript 与 TypeScript 的区别

TypeScript 是 JavaScript 的超集，扩展了 JavaScript 的语法，因此现有的 JavaScript 代码可与 TypeScript 一起工作无需任何修改，TypeScript 通过类型注解提供编译时的静态类型检查。

TypeScript 可处理已有的 JavaScript 代码，并只对其中的 TypeScript 代码进行编译。

TypeScript 安装

我们可以通过以下两种方式来安装 TypeScript：

通过 Node.js 包管理器 (npm)

通过与 Visual Studio 2012 继承的 MSI. (Click here to download)

通过 MSI 文件安装时的界面:

通过 npm 按安装的步骤：

1、安装 npm

$ curl http://npmjs.org/install.sh | sh$ npm --version2.15.1

2、安装 TypeScript npm 包：

$ npm install -g typescript

安装完成后我们就可以使用 TypeScript 编译器，名称叫 tsc，可将编译结果生成 js 文件。

要编译 TypeScript 文件，可使用如下命令：

tsc filename.ts

一旦编译成功，就会在相同目录下生成一个同名 js 文件，你也可以通过命令参数来修改默认的输出名称。

默认情况下编译器以ECMAScript 3（ES3）为目标但ES5也是受支持的一个选项。TypeScript增加了对为即将到来的ECMAScript 6标准所建议的特性的支持。

TypeScript Hello World

首先，我们创建一个 index.html 文件：

Learning TypeScript

创建 hello.ts 文件， *.ts 是 TypeScript 文件的后缀，向 hello.ts 文件添加如下代码：

alert('hello world in TypeScript!');

接下来，我们打开命令行，使用 tsc 命令编译 hello.ts 文件：

$ tsc hello.ts

在相同目录下就会生成一个 hello.js 文件，然后打开 index.html 输出结果如下：