* ##### JavaScript 概述


* JavaScript是一种轻量级的脚本语言。所谓“脚本语言”，指的是它不具备开发操作系统的能力

* JavaScript是一种嵌入式（embedded）语言。本身不提供任何与I/O（输入/输出）相关的API

* JavaScript语言是一种“*对象模型* ”语言。

* JavaScript的核心语法部分相当精简，只包括两个部分：基本的语法构造（比如操作符、控制结构、语句）和标准库（就是一系列具有各种功能的对象比如*Array*、*Date*、*Math*等）

  ​

* ###### JavaScript的发明目的

* 就是作为浏览器的内置脚本语言，为网页开发者提供操控浏览器的能力。它是目前唯一一种通用的浏览器脚本语言，所有浏览器都支持。

  ​

* ##### JavaScript 应用领域

  1.  浏览器的平台化 
  2.  Node    为这些平台开发应用程序
  3.  数据库操作
  4.  跨移动平台
  5.  内嵌脚本语言
  6.  跨平台的桌面应用程序

  ​

* ######  JavaScript 易学性

  * 学习环境无处不在   几乎所有电脑都原生提供JavaScript学习环境，不用另行安装复杂的IDE（集成开发环境）和编译器。
  * 简单性
  * 与主流语言的相似性



* ###### JavaScript 性能

  * 语法灵活，表达力强
  * 支持编译运行
  * 事件驱动和非阻塞式设计



* ######  JavaScript 引入方式

  * 内嵌式
  * 外链式



#####  注释与语句

* 输出
  * 控制台输出
  * 页面输出
  * 提示框输出

##### 变量

* 标识符（变量名，函数名）命名规则：
  1. 必须以字母、美元符号(**$**)以及下划线（**_**）开头，不能以数字开头；
  2. 名字可以包含字母、数字、美元符号或下划线。注意，在变量中不能使用连字符(***-***)和点(***.***)号；
  3. 不能使用关键字或保留字来对变量命名。
  4. 所有的变量都是大小写敏感的，变量 `x` 与变量 `X` 是不一样的；
  5. 变量命名必须见名知意，语义化，如创建一个数字变量，名字可以取名为*number*，不能使用拼音或中文命名变量；
  6. 如果变量的名字由多个单词组成，则应遵守**驼峰命名**法则，即第一个单词首字母小写，后面单词首字母大写，如一个描述人的姓名的变量，正确的变量命名应该是*personName*;
* 变量作用域
  * “局部变量”就是指所定义的变量只会在一个限定的范围内生效，通常指在某一个函数（function）内。
  * “全局变量”，它的值可以被所有的方法或函数获取到。通常将一个变量写在所有函数的外部的变量，就叫做“全局变量”，但是在函数内部，若忘记在变量名前加上`var`的话，该变量也会成为全局变量



##### 运算符与表达式

* 基本运算符

提示：自增与自减运算符都是让自身 `+1` 或 `-1`，在使用上无差别，这里以自增运算符为例。

1）、无论 `++` 运算符在变量前还是在变量后，变量自身都会 `+1`

2）、`++` 在前，先自增、再赋值；`++` 在后，先赋值，再自增

*  赋值运算符

*  关系运算符

  * ==   >   < 


  * 关系运算符描述两个变量的关系，其返回值类型为布尔类型（boolean），即 `true` 和 `false`。

* 逻辑运算符

  ​    &&   ||  !   判断几条语句成立情况的一种运算，该运算符的返回值类型为布尔类型

* 三元运算符



##### 基本数据类型

1、数值类型（number）

2、字符串类型（string）

​       ** 引号

3、布尔类型（boolean）

​      该类型只有两个值，即：

- true：表示“是”，在判断语句中可以用“非0”、“非undefined”、“非null”、“非NaN”、“字符串”、“对象”甚至是一个“函数”表示
- false：表示“否”，在判断语句中可以用数值“0”、“undefined”、“null”或“NaN”表示。

4、对象类型（object）

​       var a = new Object();    // 对象
​       var b = [1, 2, 3, 4, 5]; // 数组对象

5、函数类型（function）

​     该类型表示变量的类型为一个可运行的“函数”。

6、未定义（undefined）

【】{}

##### 类型转换

* 自动转换类型

  1.##### 强制转换

  强制转换主要指使用 `Number()`、`String()` 和  `Boolean()` 三个构造函数

  2.###### Number（）

  * 字符串、布尔值、undefined 和 null，它们都能被 Number 转成数值或 NaN（not a number 非数字）。

  *  *parseInt* （）

    ​

  3.** String()**

- **数值**：转为相应的字符串。
- **字符串**：转换后还是原来的值。
- **布尔值**：*true*转为*"true"*，false转为*"false"*。
- **undefined**：转为*"undefined"*。
- **null**：转为*"null"*。
- `String` 方法的参数如果是对象，返回一个类型字符串；如果是数组，返回该数组的字符串形式。

4. Boolean()

- **undefined**
- **null**
- **-0**
- **0**或**+0**
- **NaN**
- **''**（空字符串）





##### 类型分类

通过按值来访问数据，其类型可分为两大类：

- 值类型：数值、布尔值、null、undefined...
- 引用类型：对象、数组、函数...





### 程序结构

程序可以分为三种基本结构：顺序结构、分支结构、循环结构。





### 数值

所有的数字都是以 64位浮点数的形式存储的

JavaScript能精确表示的数值范围在*-(2<sup>53</sup>-1)到2<sup>53</sup>-1*之间。

“*Math.pow(binary,power)*”，其中“binary”是指“底数”，函数中的参数意思就是“binary”的“power”次幂（次方），如“Math.pow(5,3)”得出的结果就是125，表示5的3次方。

.toFixed()

`parseInt()` 方法对内部的数值依次向右转换，一旦遇到**“非数字 ”**的字符（甚至包含小数点***“.”***）立即将之前取到的值返回。

Number.prototype.toPrecision()





### 字符串

* 定义字符串 “”引号   str.length；
* `split()` 和 `join()`将字符串转换为数组
* 转义字符：\0（或：\u0000）用于表示：null
* * \n（或：\u000A）用于表示：换行符
  * \\ （或：\u005C）用于表示：反斜杠



##### 字符的 Unicode 表示法

* 每个字符在JavaScript内部都是以16位（即2个字节）的UTF-16格式储存。也就是说，JavaScript的单位字符长度固定为16位长度，即2个字节。
* s.charCodeAt(0)).toString(16)    转换为字符数字编码值
* var s = String.fromCharCode(    )，数字编码转换为字符串

##### 字符串包装对象

在 JavaScript中对象主要分为两大类，一类称作“**包装对象**”，一类称作“**内置对象**”。

   1.从编码角度讲，它们的区别是在使用了 `Object()` 方法后是否还全等于自身，若不等于自身，那就是一个包装对象；若等于自身，那就是一个内置对象。

1. 直接typeof查看对象类型，如果为object，则为内置对象，否则为包装对象。



#####字符串对象方法

* charAt（）返回指定字符位置

* 字符串查询

* * indexOf（“匹配值”，开始位置）从开始位置向后匹配     无 返回-1
  * lastIndexOf（“匹配值”，开始位置）从开始位置向前匹配   无 返回-1
  * match() 返回数组，无返回null
  * search（） 无 返回-1
  * 查询头部  /^http/.test(website) ;
  * 查询尾部 /com$/.test(website)；

* 字符串拼接

  * concat    var s1 = 'a', s2 = 'b';
  * +

* 字符串截取

  * slice（a，b）
    * 第一个参数是开始位置，第二个参数是结束位置（不含该位置），如果省略第二个参数，则表示从指定位置开始截取到末尾。
    * 如果参数是负值，表示从结尾开始倒数计算的位置，即该负值加上字符串长度。
    * 如果第一个参数大于第二个参数，**slice** 方法返回一个空字符串。
  * subString()
    * 它的第一个参数是开始位置，第二个参数是结束位置（不含该位置）。
    * 如果省略第二个参数，则表示从指定位置开始截取到末尾。
    * 如果第二个参数大于第一个参数，**substring** 方法会自动更换两个参数的位置。
    * 如果参数是负数，**substring** 方法会自动将负数转为0。
  * **substr** 
    * 方法用于字符串截取，不改变原字符串。
    * 它的第一个参数是开始位置，第二个参数是结束位置（不含该位置）。
    * 如果省略第二个参数，则表示从指定位置开始截取到末尾。
    * 如果第二个参数大于第一个参数，**substring** 方法会自动更换两个参数的位置。
    * 如果第一个参数是负数，表示倒数计算的字符位置。如果第二个参数是负数，将被自动转为0，因此会返回空字符串。

* 字符串去除空格   .trim()

*  字符串大小写转换   

  * 'Hello World'.toLowerCase();
  * 'Hello World'.toUpperCase();

* 字符串替换

  * **replace** 方法用于字符串替换，其语法形式为：`replace(search, replacement)`    
  * .raplace(/g   /,)

* Base64转码

  * **btoa()**

    将字符串或二进制值转为Base64编码

  * **atob()**

    将Base64编码转为原来的编码




### 数组

* JavaScript集合类型主要使用数组，数组为一个特殊对象。

* type-object   二维数组

* ##### 数组空位

  * in  适用于对象，也适用于数组
  * 存在元素   true  ，不存在 为fault
  * ​

* isArray（）

* ##### 添加数组元素

  * `push()`：在数组的末端添加一个或多个元素，并返回添加新元素后的数组长度*（ 改变原数组）*
  * `unshift()`：在数组的开始位置添加一个或多个元素，并返回添加新元素后的数组长度*（ 改变原数组）*
  * `apply()`：合并数组（只能合并两个）*（ 改变原数组）*
  * `concat()`：合并数组（允许合并多个数组） *（ 不改变原数组）*
  * 下标法

* ##### 删除数组元素

  * `pop()`：删除数组最后一个元素*（ 改变原数组）*。

  * `shift()`：删除数组第一个元素*（ 改变原数组）*。

  * `splice()`：范围删除*（ 改变原数组）*。

    *  *splice* 方法最为灵活，不仅可以范围删除数组元素，还可以实现数组元素的插入和替换。splice(location, count, items...)

    * 第一个参数是删除的起始位置，第二个参数是被删除的元素个数。如果后面还有更多的参数，则表示这些就是要被插入数组的新元素。

    * 该方法的第一个参数可以为负数（但是第二个不能，因为它表示长度），表示从数组末端开始计数，开始计数的值为“**-1**”。

    * var arr = [1, 2, 3, 4, 5];

      arr.splice(-3, 2); // 删除元素：3，4

* ##### 截取数组元素

  * .slice(startIdx, endIdx);
  * 第一个参数为起始位置（从下标0开始），第二个参数为终止位置（不包括该位置）。如果省略第二个参数，则一直返回到原数组的最后一个成员。

* ##### 数组排序

  * sort（）
  * =arr.sort(funciton(n1,n2){ return n2-n1降序    n1.score-n2.score 升序});
  * reverse() 倒序排列

* ##### 操作数组元素

  * .map()

  * ```
    var res = nums.map(function (item, index, arr) {
        return item * 2;
    });
    var newArr = nums.map(num => num * 2);
    console.log(newArr); // [2, 4, 6, 8]
    ```

* ##### 过滤数组

  * .filter()

  *    filArr = arr.filter(function (num) {
            return num % 2 == 0;
        });
        var names_li = names.filter(function (item, index, arr) {
        return /^李/.test(item);
        });

* ##### 数组遍历

  * `for` 循环遍历数组元素

  * `for-in` 循环遍历数组元素

  * `forEach()` 方法遍历数组元素

    * ```
      nums.forEach(function (item, index, arr) {
          console.log(item);
      });
      ```

var aLeng = Array.prototype.push.apply(arr1, arr2);

split ()字符串转数组

slice() 字符串/数组 截取

splice() 数组 替换 删除  插入

### 函数

* 用关键字function定义的一段具有独立作用域，能被反复执行的语句块，或者函数就是功能。
* 函数被定义是 产生作用域链，便于变量查找0-3

##### 值传递与地址传递

* 如果参数为“**包装对象**”，即为值传递，如果参数为“**内置对象**”，即为地址传。
* 地址传递修改原始值



自调用函数、匿名函数

```
//将类似数组转换成真正的数组
var newArr = Array.prototype.slice.call(arguments);
```



作用域详解

执行上下文   作用域链

AO

GO

##### 立即执行函数

没有函数声明 在一次执行过后立即释放。适合初始化工作。

* 只有表达式才能被执行符号执行；
* 表达式   
* 123；
* var demo = function（）{}  函数表达式    
* var demo = function（）{}（）； 变成一次性了，demo执行后失去对函数的索引，执行后销毁，变成空的demo对象
* （）括号括起来的都叫表达式

（funciton（）{}（））；





代码如下:

(function foo() {...})    // 这里是故意换行，实际上可以和下面的括号连起来
();

这就等价于：

 

var foo = function () {...};    // 这就不是定义，而是表达式了。
foo();



闭包，当内部函数被保存到外部时，将会生成闭包。闭包会导致原有作用域链不释放，造成内存泄漏

##### 闭包的作用

* 实现公有变量

  fuction add(){

​       var count =  0;

​      function demo(){

​             count   ++；

​              console.log(count);

​      }

​      return demo;

}

   var couter =  add();

  couter();

 couter();

* 可以做缓存

​      function test(){

  var num = 100;

  function a(){

​     num ++;

​    console.log(num);

}

  function b(){

   num --;

   console.log(num)

}

return[a,b];

}

var myArr = test();

myArr[0]();  //101

myArr[1]();  //100





function eater(){

​     var food = "";

   var obj = {

​      var food = "";

​      var obj = {

​      eat : funciton(){ console.log();

​        food = "";},

​      push: funciton(myfood){ console.log();

​        food = myfood}

}

}

return obj;

}

 var eater1 = eater();

eater1.push(banana);

eater1.eat();

* 可以实现封装，属性私有化
* 模块化开发，方式污染全局变量









### 返回值

 **return**关键字，除了能够返回值以外，另外一个作用便是终止函数，**return**关键字后的代码不会执行。

 函数返回值只能是一个，不能有多个返回值

### 函数类型

##### 1.变量函数：

```javascript
var function_name = function(argument) {
	// body...
}
```

##### 2.自调用函数 

   （function(){         }）（）； 

##### 3.构造函数

var function_name = new Function(argument);

##### 4.构造函数（对象）

	// 创建函数模板
	function Person(name, sex, age) {
		this.name = name;
		this.sex  = sex;
		this.age  = age;
	
		this.skill = function() {
			return `动感光波`;
		}
	}
	
	// 实例化函数对象
	let per = new Person('小明', '男', 25);
	console.log(`
		姓名：${per.name}
		性别：${per.sex}
		年龄：${per.age}
		技能：${per.skill()}
		`);
##### 5.递归函数

调用自身，

	// 5! -> 5 * 4 * 3 * 2 * 1
	function factorial(n) {
	if (n == 0 || n == 1) {
		return 1;
	}else {
		return n * factorial(n - 1);
	}
	}
	
	factorial(5);  // 120

##### 6.闭包函数

* 在函数外部无法读取函数内部声明的变量。
* 如果出于种种原因，需要得到函数内的局部变量。正常情况下，这是办不到的，只有通过变通方法才能实现。那就是在函数的内部，再定义一个函数。
* * 这就是JavaScript语言特有的”链式作用域”结构（chain scope），子对象会一级一级地向上寻找所有父对象的变量。所以，父对象的所有变量，对子对象都是可见的，反之则不成立。
* * 由于在JavaScript语言中，只有函数内部的子函数才能读取内部变量，因此可以把闭包简单理解成 “**定义在一个函数内部的函数即为闭包**”。
* * 闭包的最大用处有两个，一个是可以读取函数内部的变量，另一个就是让这些变量始终保持在内存中，即闭包可以使得它诞生环境一直存在。


##### 闭包

 当内部函数被保存到外部时，将会生成闭包。闭包导致原作用域链不释放，造成内存泄漏

##### 闭包的作用

1.实现公有变量  函数累加器

2.可以做缓存

3.可以实现封装，属性私有化

4.模块化开发，防止污染全局变量







### 对象

* ，所谓对象，就是一种 **无序** 的数据集合，由若干个“ **键值对** ”（key-value，亦称属性名值对、成员等）构成。


* 面向对象编程具有灵活性、代码的可重用性、模块性等特点，容易维护和开发，非常适合多人合作的大型软件项目。
  * “对象”是单个实物的抽象。
  * “对象”是一个容器，封装了“属性”（property）和“方法”（method）。

##### 1.原始对象 

```

// 1、原始模式，Object构造函数方式
var obj = new Object();
obj.name = 'Petter';
obj.age  =  28;
obj.showName = function() { alert(this.name); }
// 2、原始模式，对象字面量方式
var obj = {
name: 'Petter',
age: 28,

  	showName: function() {
  	  alert(this.name);
}
}
```
##### 2.工厂模式

	function createPerson(name, age) {
	var obj = new Object();
	obj.name = name;
	obj.age  = age;
	obj.showName = function() {
		alert(obj.name);
	}
	return obj;
	}
	
	var obj1 = createPerson('Admin', 22);
	var obj2 = createPerson('Petter', 28);


##### 3.构造函数

	function Person(name, age) {
	this.name = name,
	this.age  = age,
	this.showName = function() {
		alert(this.name);
	}
	}
	var per1 = new Person("李强", 24);
	var per2 = new Person("李伟", 28);
##### 4.原型模式

Javascript规定，每一个构造函数都有一个 `prototype` 属性，指向另一个对象。这个对象的所有属性和方法，都会被构造函数的实例继承。意味着，我们可以把那些不变的属性和方法，直接定义在`prototype`对象上。

提示：这里需要注意的是原型属性和方法的共享，即所有实例中都只是引用原型中的属性方法，任何一个地方产生的改动会引起其他实例的变化，因为它们指向同一块内存。

    // 1、原型模式，直接定义prototype属性
    function Person () {}
    Person.prototype.name = 'Henrry Lee';
    Person.prototype.age = 26;
    Person.prototype.showName = function () { alert(this.name); };
    // 2、原型模式，字面量定义方式
    function Person () {}
    Person.prototype = {
    name: 'Jack',
    age: 18,
    showName: function () { alert(this.name); }
    };
    var p1 = new Person(); //name='Jack'
    var p2 = new Person(); //name='Jack'
 ##### 5.混合模式



    // 原型构造组合模式，
    function Person (name, age) {
    this.name = name;
    this.age = age;
    }
    
    Person.prototype = {
    hobby: ['running', 'game'],
    showName: function () { alert(this.name); },
    showAge: function () { alert(this.age); }
    };
    
    var p1 = new Person('Jack', 20); 
    //p1:'Jack',20; proto: ['running','game'],showName,showAge
    var p2 = new Person('Mark', 18); 
##### 对象操作（增删改查）

1.增 phone.color = 'black';

2.删 delete phone.company; // true

3.改 phone.pubDate = '2016-09-11';

4.查 phone.brand; // "iPhone"
​        phone.model; // "iPhone7 Plus"



##### 原始值

 



### 原型

定义：原型是function对象的一个属性，他定义了构造函数制造出来的对象的公共祖先。通过该构造函数产生的对象，可以继承该原型的属性和方法

### 原型链

JavaScript 原生提供一个Object对象，所有其他对象都继承自这个对象。Object本身也是一个构造函数，可以直接通过它来生成新对象。

- prototype：这个属性是一个指针，指向一个对象（通过该构造函数创建实例对象的原型对象）
- \_\_proto__：这个属性是一个内部指针，指向原型对象（构造函数









### 对象继承

##### 1.构造函数绑定



    function Cat(name,color){
    // 继承 Animal
    Animal.apply(this, arguments);
    this.name = name;
    this.color = color;
    }
    var cat = new Cat("小黄", "黄色");
    console.log(cat.species); // 动物


##### 2.prototy模式

// 将Cat的prototype指向Animal的一个实例
// 它相当于完全删除了prototype 对象原先的值，然后赋予一个新值。
Cat.prototype = new Animal();

// 任何一个prototype对象都有一个constructor属性，指向它的构造函数。
// 如果没有这一行，Cat.prototype.constructor是指向Animal的；
// 加了这一行以后，Cat.prototype.constructor指向Cat。
Cat.prototype.constructor = Cat;

var cat = new Cat("小黄","黄色");
console.log(cat1.species); // 动物

提示：如果替换了prototype对象，那么，下一步必然是为新的prototype对象加上constructor属性，并将这个属性指回原来的构造函数。





##### 3.利用空对象作为中介

 

```javascript
var F = function(){};
F.prototype = Animal.prototye;
Cat.prototype = new F();
Cat.prototype.constructor = Cat;

console.log(Animal.prototype.constructor); // Animal
```

 

我们将上面的方法，封装成一个函数，便于使用。

```javascript
function extend(Child, Parent) {
　　var F = function(){};
　　F.prototype = Parent.prototype;
　　Child.prototype = new F();
　　Child.prototype.constructor = Child;
　　Child.uber = Parent.prototype;
}
```

使用的时候，方法如下：

```javascript
extend(Cat, Animal);
var cat = new Cat("小黄","黄色");
console.log(cat1.species); // 动物
```

另外，说明一点，函数体最后一行：

```javascript
Child.uber = Parent.prototype;
```

意思是为子对象设一个uber属性，这个属性直接指向父对象的prototype属性。（uber是一个德语词，意思是"向上"、"上一层"。）这等于在子对象上打开一条通道，可以直接调用父对象的方法。这一行放在这里，只是为了实现继承的完备性，纯属备用性质。



##### 4.拷贝继承

首先，还是把Animal的所有不变属性，都放到它的prototype对象上。

```javascript
function Animal(){}
Animal.prototype.species = "动物";
```

然后，再写一个函数，实现属性拷贝的目的。

```javascript
function extend(Child, Parent) {
    var p = Parent.prototype;
    var c = Child.prototype;
    for (var key in p) {
      c[key] = p[key];
    }
    c.uber = p;
}
```

这个函数的作用，就是将父对象的prototype对象中的属性，一一拷贝给Child对象的prototype对象。

使用的时候，这样写：

```javascript
extend2(Cat, Animal);
var cat1 = new Cat("小黄","黄色");
alert(cat1.species); // 动物
```

## 









### 非构造函数继承

请问怎样才能让"医生"去继承"中国人"，也就是说，我怎样才能生成一个"中国医生"的对象？

这里要注意，这两个对象都是普通对象，不是构造函数，无法使用构造函数方法实现"继承"。

##### 浅拷贝

    function extendCopy(parent) {
    var child = {};
    for (var key in parent) { 
    child[key] = parent[key];
    }
    child.uber = parent;
    return child;
    }



##### 深拷贝

    function deepCopy(parent, child) {
    var child = child || {};
    for (var key in parent) {
        if (typeof parent[key] === 'object') {
            child[key] = (parent[key].constructor === Array) ? [] : {};
            // 递归调用
            deepCopy(parent[key], child[key]);
        } else {
            child[key] = parent[key];
        }
    }
    return child;
    }


### 函数对象

**Date** 对象可以作为普通函数直接调用，返回一个代表当前时间的字符串。即使带有参数，**Date** 作为普通函数使用时，返回的还是当前时间。

Date(2017, 07, 16)

// Tue Jul 04 2017 10:15:15 GMT+0800 (CST)





提示：这里需要注意的是原型属性和方法的共享，即所有实例中都只是引用原型中的属性方法，任何一个地方产生的改动会引起其他实例的变化，因为它们指向同一块内存。







### 延时调用

setTimeout(function, delay)

 `clearInterval(function, delay)`。

	interval = setInterval(function(){
	if (n == 0) {
		this.clearInterval(interval);
		console.log('定时器停止！');
	}else {
		console.log(--n);
	}
	}, 1000);


###会话存储

会话存储（sessionStorage）的键值在浏览器关闭后会被清除

// 临时存储数据

##### * sessionStorage.setItem("name", "Henrry Lee");

// 获取临时存储的数据

##### var msg = sessionStorage.getItem("name");

##### sessionStorage.removeItem('name')

##### sessionStorage.clear()



### 本地存储

localStorage.setItem('name', "Henrry Lee");



监听函数的格式如下：

```javascript
window.addEventListener('storage', function(e) {
	console.log(e.key);
	console.log(e.oldValue);
	console.log(e.newValue);
	console.log(e.url);
});
```

转成JSON字符串格式
var strObj = JSON.stringify(obj);
localStorage.setItem("userInfo", strObj);

将JSON字符串转为JS对象
var jsObj = JSON.parse(storageStrObj);



### DOM

DOM的最小组成单位叫做节点（Node），文档的树形结构（DOM树），就是由各种不同类型的节点组成。

最顶层的节点就是 **document** 节点，它代表了整个文档。它构成树结构的根节点（root node）

除了根节点以外，其他节点对于周围的节点都存在三种关系。

- **父节点关系 parentNode**：直接的那个上级节点
- **子节点关系 childNodes**：直接的下级节点
- **同级节点关系 sibling**：拥有同一个父节点的节点

NodeList  实例对象是一个“类似数组”的对象，它的成员是节点对象。

*document.querySelectorAll* 方法返回的是一个静态集合。DOM内部的变化，并不会实时反映在该方法的返回结果之中。



## 节点生成

  以下方法可以用于生成DOM节点：

- **document.createElement()**：该方法用来生成HTML元素节点，该方法的参数为元素的标签名，即元素节点的tagName属性。
- **document.createTextNode()**：该方法用来生成文本节点，参数为所要生成的文本节点的内容。
- **document.createAttribute()**：该方法生成一个新的属性对象节点，该方法的参数是属性的名称。属性生成后可以用value属性为其赋值。

HTML元素包括标签名和若干个键值对，这个键值对就称为“属性”（attribute）。

**Element.getAttribute()**

该方法返回当前元素节点的指定属性。如果指定属性不存在，则返回null。参数为指定的属性名称。



##### DOM Element

**Element.innerHTML**：该属性返回该元素包含的HTML代码。该属性可读写，常用来设置某个Element节点的内容。如果将该属性设为空字符串，等于删除了它包含的所有节点。



##### 插入节点

- **Element.appendChild()**

  该方法接受一个节点对象作为参数，将其作为最后一个子节点，插入当前节点。

- **Element.before()**

  该方法用于在当前节点的前面，插入一个同级节点。如果参数是节点对象，插入DOM的就是该节点对象；如果参数是文本，插入DOM的就是参数对应的文本节点。

- **Element.after()**

  该方法用于在当前节点的后面，插入一个同级节点。如果参数是节点对象，插入DOM的就是该节点对象；如果参数是文本，插入DOM的就是参数对应的文本节点。





##### 替换节点

- **Element.replaceWith()**

  该方法使用参数指定的节点，替换当前节点。如果参数是节点对象，替换当前节点的就是该节点对象；如果参数是文本，替换当前节点的就是参数对应的文本节点。

- **Element.replaceChild()**

  该方法用于将一个新的节点，替换当前节点的某一个子节点。它接受两个参数，第一个参数是用来替换的新节点，第二个参数将要被替换走的子节点。它返回被替换走的那个节点。

#####  DOM Text

- **nodeValue**：设置/获取文本值，只有文本节点和注释节点才有 nodeValue 属性，元素节点要获取文本值可通过 *el.firstChild.nodeValue* 获取。
- **Element.textContent**：设置/获取当前元素节点及其后代节点文本内容。该属性会忽略标签。
- **Element.innerText**：设置/获取当前元素节点及其后代节点文本内容。





##### DOM Style







### 正则表达式

正则表达式（regular expression）是一种表达字符串结构的方法。它现在的主要用途就是给定一个模式，然后让指定字符串来匹配这个模式。常见的用途有“关键字过滤”、“用户表单输入”、“数据内容筛选”等

新建正则表达式有两种方法。一种是使用字面量，以斜杠表示开始和结束;另一种是使用RegExp构造函数。

 第一种方法在编译时新建正则表达式，第二种方法在运行时新建正则表达式。

- i，表示忽略大小写
- g，表示全局匹配，否则只返回第一个匹配的值
- m，表示多行匹配

另一类是与修饰符无关的属性，主要是下面两个。

- **lastIndex**：返回下一次开始搜索的位置。该属性可读写	，但是只在设置了 `g` 修饰符时有意义。
- **source**：返回正则表达式的字符串形式（不包括反斜杠），该属性只读。



* a、test()

  正则对象的`test`方法返回一个布尔值，表示当前模式是否能匹配参数字符串。

* b.exec()

正则对象的 **exec** 方法，可以返回匹配结果。如果发现匹配，就返回一个数组，成员是每一个匹配成功的子字符串，否则返回 `null`。

**exec** 方法的返回数组还包含以下两个属性：

- **input**：整个原字符串。 
- **index**：整个模式匹配成功的开始位置（从0开始计数）。

字符串对象的方法之中，有4种与正则对象有关。

- **match()**：返回一个数组，成员是所有匹配的子字符串。
- **search()**：按照给定的正则表达式进行搜索，返回一个整数，表示匹配开始的位置。
- **replace()**：按照给定的正则表达式进行替换，返回替换后的字符串。
- **split()**：按照给定规则进行字符串分割，返回一个数组，包含分割后的各个成员。

元字符:指的是用一些规定的字符来表示特定的字符。

\. 、\r 、 \n 、\n 、[]、{}、\、+ 、- 、* 、$ 、^ 、()

 

除开空格和空白 回车换行   .

开始位置字符或脱字符“^” 如果在^在中括号中表示取反;

结束位置字符“$”

字符选择“[]” :匹配其中一个

选择符“|”

连字符“-”

匹配组“()”

匹配零次或一次“?”

匹配零次或多次“*”

至少匹配一次“+”

匹配次数限制“{}”

通过“?”可以匹配字符串中的指定字符是否出现

这种匹配方式我们在“?”用来匹配手机号码中已经见到过，但它主要有三种表现形式：

{m} 匹配的内容连续出现m次

{m,} 匹配的内容至少出现m次

{m,n} 匹配的内容至少出现m次，至多出现n次



 ([\u4E00-\u9FFF]+)一个或多个汉字

中间是汉字的Unicode编码范围

([0-9]+)一个或多个数字







\d 匹配0-9之间的任一数字，相当于[0-9]。

\D 匹配所有0-9以外的字符，相当于[^0-9]。

\w 匹配任意的字母、数字和下划线，相当于[A-Za-z0-9_]。

\W 除所有字母、数字和下划线以外的字符，相当于[^A-Za-z0-9_]。

\s 匹配空格（包括制表符、空格符、断行符等），相等于[\t\r\n\v\f]

\S 匹配非空格的字符，相当于[^\t\r\n\v\f]。

\b 匹配词的边界。

\B 匹配非词边界，即在词的内部。

验证用户密码:以字母开头，长度在6~18之间，只能包含字符、数字和下划线:(/^[a-zA-Z]\w{5,17}$/)

只能输入汉字：(/^[\u4e00-\u9fa5]{0,}$/)

验证手机号码：(/^((\d{3,4}-)|\d{3,4}-)?\d{7,8}$/)或（/^1(3|4|5|7|8)\d{9}$/）

验证固定电话和手机号码：（/^((0\d{2,3}-\d{7,8})|(1[3584]\d{9}))$/）

验证身份证号（15位或18位数字）：(/^[1-9]\d{14}|^[1-9]\d{17}|^[1-9]\d{16}x/)

匹配ip地址：(/\d+\.\d+\.\d+\.\d+/)

匹配档压缩包：(/^[\w]+\.zip|rar|gz/)

验证Email地址：(/^\w+@[a-z0-9]+\.([a-z]){1,3}$/)或(/^\w+([-+.]\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$ /)或(/^\w+([-+.]\w+)*@[0-9a-z)+\.(a-z){1,3}$/)

URL：(/(\w+):\/\/([\w.]+)\/(\s*)/)

匹配腾讯QQ号：(/^[1-9][0-9]{4,}/)

匹配中国邮政编码：(/[1-9]\d{5}(?!\d)/)

匹配html标签的正则表达式：(/<(.*)>(.*)<\/(.*)>|<(.*)\/>/)

匹配首尾空格的正则表达式：(/(^\s*)|(\s*$)/)













1、String.prototype.match()

2、String.prototype.search()

3、String.prototype.replace()

**replace** 方法的第二个参数可以使用美元符号 `$` ，用来指代所替换的内容。

- **$&**：指代匹配的子字符串。
- ***$`***：指代匹配结果前面的文本。
- ***$'*** ：指代匹配结果后面的文本。
- ***$n***：指代匹配成功的第*n*组内容，*n*是从1开始的自然数。
- ***$$***：指代美元符号*$*。

4、String.prototype.split()



### canvas

在使用Canvas前，用 `canvas.getContext` 来测试浏览器是否支持Canvas：

`<canvas id="test-canvas" width="500" heigth="300">

<p>你的浏览器不支持Canvas</p>
</canvas>`

* var canvas = document.getElementById('test-canvas');
* `getContext('2d') ` 方法让我们拿到一个 **CanvasRenderingContext2D** 对象，所有的绘图操作都需要通过这个对象完成。

Canvas元素绘制图像的时候有两种方法，分别是

- ctx.fill() ：填充
- ctx.stroke()：绘制边框

在进行图形绘制前，要设置好绘图的样式：

- ctx.fillStyle：填充的样式
- ctx.strokeStyle：边框样式

你还可以设置边框宽度：

- ctx.lineWidth

## 文字

- 填充文字：*context.fillText(text,x,y)*
- 绘制文字轮廓：*context.strokeText(text,x,y)*

> 参数解读：

- `text`：要绘制的文字
- `x`：文字起点的x坐标
- `y`：文字起点的y坐标

> 其他配置：

- *ctx.font*：设置字体样式
- *ctx.textAlign*：设置字体水平对齐方式（*start、end、left、right、center*）

## 矩形

- 填充矩形：*context.fillRect(x,y,width,height)*
- 绘制矩形：*strokeRect(x,y,width,height)*

清除矩形区域：*context.clearRect(x,y,width,height)*



## 圆弧

- 绘制圆弧：*context.arc(x, y, radius, starAngle,endAngle, anticlockwise)*

> 参数解读：

- `x`：圆心x坐标
- `y`：圆心y坐标
- `starAngle`：开始角度
- `endAngle`：结束角度
- `anticlockwise`：是否逆时针（ *true* 为逆时针，*false* 为顺时针）

## 线段

- *context.moveTo(x,y)*
- *context.lineTo(x,y)*

##  线性渐变

- 创建线性渐变：*var lg =ctx.createLinearGradient(xStart,yStart,xEnd,yEnd)*
- 颜色节点：*lg.addColorStop(offset,color)*

### 事件

1）、直接将代码写在HTMl上，在页面标签元素的 “*on-*” 属性上添加

2）、通过DOM元素添加

document.getElementsByTagName('input')[0].oninput = function() {

3）、通过实例化过后的Element对象添加

var ipt = document.getElementsByTagName('input')[0];

4）、对实例化过后的Element对象进行监听

    var ipt = document.getElementsByTagName('input')[0];
    var btn = document.getElementsByTagName('button')[0];
    ipt.addEventListener('input', function() {
    // 事件处理部分
    // ... 
    alert("处理input事件！");
    }, false);


类似数组  相关操作

绑定事件方法

addEventListener



# 事件传播

  当一个事件发生以后，它会在不同的DOM节点之间传播，这种传播会使得一个事件在多个节点上触发。事件传播分成三个阶段：

- 第一阶段：从window对象传导到目标节点，称为“捕获阶段”
- 第二阶段：在目标节点上触发，称为“目标阶段”
- 第三阶段：从目标节点传导回window对象，称为“冒泡阶段”











### BOM

**BOM**（Browers Object Model，浏览器对象模型）是浏览器为JavaScript提供的一个API（Application Programming Interface，应用编程接口），所以它不是原生JavaScript提供的。通过BOM我们可以访问和设置浏览器的一些属性和函数。

window对象下主要包含了以下子对象：

#### windows

浏览器窗口相关的主要属性有以下（数值表示的单位统一为像素）:

- **window.innerWidth**：浏览器窗口的可见宽度
- **window.innerHeight**：浏览器窗口的可见高度
- **window.outerWidth**：浏览器窗口的实际宽度（包括浏览器菜单和边框）
- **window.outerHeight**：浏览器窗口的实际高度（包括浏览器菜单和边框）
- **window.window.pageXOffsett**：浏览器窗口滚动条水平滚动的距离
- **window.pageYOffset**：浏览器窗口滚动条垂直滚动的距离

    /隐藏滚动条/
    body::-webkit-scrollbar {
    display: none;
    }
    window.open() 方法用于打开一个新的窗口（或标签页），而window.close() 用于关闭当前窗口，他们同样可以将方法前的window对象省略不写，也能达到同样的方法效果。

* `getSelection()` 方法返回一个 **Selection** 对象，表示用户现在选中的文本。而用这个方法的 `toString()` 方法可以用于返回被选中的文本。



#### document：文档对象

- **frames**：浏览器的框架（如iframe和现在废弃了的frameset）

- **history**：浏览器浏览历史对象

- **location**：浏览器页面所处位置对象

- **navigator**：浏览器信息导航对象

  ​

#### screen：浏览器屏幕对象

和屏幕相关的还有以下属性：

- **screenLeft**：返回当前浏览器窗口距离屏幕左侧的像素数值
- **screenTop**：返回当前浏览器窗口距离屏幕上侧的像素数值
- **screenX**：作用和screenLeft相同
- **screenY**：作用和screenTop相同



#### history

- **1）、history.back()**

  返回到上一个访问页面，等同于浏览器的后退键。用于制作手机客户端左上角的返回按钮是个不错的选择。不要将返回的按钮设置为一个超链接，因为有的时候不知道是从哪个页面跳到这个页面的，如果用超链接的方式有时是无法正确回到上一个页面的。

- **2）、history.forward()**

  前进到下一个访问页面，等同于浏览器的前进键。

- **3）、history.go()**

  相对当前记录后退或前进到第几个记录，参数为一个“正负整数”。