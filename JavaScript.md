# JavaScript

---

## 1.JavaScript简介

​	JavaScript简称JS，是一种计算机编程语言，由Brendan Eich于1995年发明，作为开发Web页面的脚本语言而出名，如今也运用于很多非浏览器环境中。

​	JavaScript是一种运行在客户端的脚本语言，如今也可以借助Node.js技术进行服务器端编程。

​	是一种脚本语言（解释型语言），运行时被编译器逐行翻译成机器语言并运行。

---

## 2.主要功能

```
1. 嵌入动态文本于HTML页面。
2. 对浏览器事件做出响应。
3. 读写HTML元素。
4. 在数据被提交到服务器之前验证数据。
5. 检测访客的浏览器信息。
6. 控制cookies，包括创建和修改等。
7. 基于Node.js技术进行服务器端编程。
```

---

## 3.浏览器的两部分

### 3.1 渲染引擎

​	俗称==内核==，用来解析HTML与CSS，比如chrome的blink，老版本的webkit。

### 3.2 JS引擎

​	也称==JS解释器==，用来读取网页中的JavaScript代码，对其处理后运行，如浏览器的V8。

​	浏览器本身并不会执行JS代码，而通过内置JavaScript引擎执行JS代码。JS引擎执行代码时逐行解释每一句原码，转换为机器语言，然后交由计算机执行。

---

## 4.JavaScript的组成

###  4.1 EMCAScript

​	由EMCA设计的一种标准化的脚本语言，JavaScript和JScript都是这个语言的一种扩展。

### 4.2 DOM

​	DOM(Document Object Model 文档对象模型)，一种与平台和语言无关的应用程序接口(API)，可以动态地访问程序和脚本。是W3C组织推荐的处理可扩展标记语言的==标准编程接口==。通过DOM提供的接可以对页面元素进行操作(大小、颜色、位置等)。

### 4.3 BOM

​	BOM(Browser Object Model 浏览器对象模型)，提供了独立于内容、可以与<span style="color:purple;">浏览器窗口</span>进行互动的对象结构。通过BOM可以操作浏览器窗口，如弹出框、控制浏览器跳转、获取分辨率等。

---

## 5.JS三种书写方式

### 5.1 行内式

​	行内式的JS，直接写在元素内部

​	例如：点击“唐伯虎”按钮，网页弹出内容为“秋香姐”的提示框

```html
<input type=“button” value=“唐伯虎” onclick=“alert('秋香姐')”>
```



### 5.2 内嵌式

写在\<head>\</head>内部，用\<script>\</script>标签包裹

例如：打开网页，弹出内容为“沙漠骆驼”的提示框

```html
<head>
    <script>
        // js中推荐使用单引号
        alert('沙漠骆驼');
    </script>
</head>
```



### 5.3 外部js文件引入

例如：引入js/flexible.js，\<script>标签中不再含有内容

```html
<head>
    <script src="js/flexible.js"></script>
</head>
```

---

## 6.输入输出语句

输入输出语句有：弹出警示框、弹出输入框、控制台日志等

```javascript
// 弹出警示框
alert('如果我是DJ');
// 浏览器控制台打印输出信息，供程序员查看 console=控制台，log=日志
console.log(msg);
// 浏览器弹出输入框，用户可以输入
prompt("请输入您的年龄");
```

---

## 7.变量语句

### 7.1 变量声明与赋值

声明变量age，为其赋值18，在控制台中打印

```javascript
// 先声明再赋值
var age;
age = 18;
console.log(age);
// 或直接声明且初始化
var name = 'pig老师';
```

### 7.2 一次输出多个变量

1.用逗号隔开多个变量

```html
<script>
    var age = 18;
    var name = 'pig';
    console.log(age,name);
</script>
// >18 pig   中间会用一个空格隔开 
```

2.用加号连接多个变量

```html
<script>
    var age = 18;
    var name = 'pig';
    console.log(age+name);
</script>
// 18pig   数字+字符串，中间不隔开，字符串+字符串同理

<script>
    var age = 18;
    var name = 'pig';
    var year = 3;
    console.log(age+year);
</script>
// >21      数字+数字，直接输出相加结果
```

3.若需要一次多行输出，则用=='\n'==换行

```html
<script>
    var age = 18;
    var year = 3;
    console.log(age+'\n'+year);
</script>
/* > 18
	 3 */
```

### 7.3 给变量赋予输入框的值

```html
<script>
    var name = prompt("请输入您的姓名");
    alert(name);
</script>
/* 
	输入：刘德华
	提示信息：刘德华
*/

```

### 7.4 变量命名规范

1. 变量名可以包括==_(下划线)、$、数字、字母==（区分大小写）

2. 不能以==数字==开头，不能以关键字为变量名

   ```html
   <script>
       var 18name;// 错误的，用数字开头
       var var； 
   </script>
   ```

3. [小驼峰](https://blog.csdn.net/weixin_42959704/article/details/124942191)命名法，非首个单词的首字母大写

   ```html
   <script>
       var myFirstName; 
   </script>
   ```

4. 某些浏览器中 ==name== 有特殊含义，尽量避免使用name作变量名

5. ==项目命名==：全部采用小写，用下划线分割

   示例：my_project_name

6. ==JS文件==命名：小驼峰式

7. ==常量==：全部大写，用_分割

   示例：MAX_SIZE

8. ==函数==：小驼峰，且尽量用动词作首单词

9. ==类==的成员：

   公共属性和方法：跟变量和函数的命名一样

   私有属性和方法：前缀为_(下划线)，后面跟公共属性和方法一样

10. ==模块==：应以!开始，确保模块忘记最后包含分号时，合并后发生错误

11. ==构造函数==：给对象原型分配方法，而不是使用一个新对象覆盖原型。

    覆盖原型会导致继承出现问题：重设原型将覆盖原有原型。

### 7.5 其他注意事项

 1. 只声明，不初始化，则console.log()结果为undefined，而不声明则会报错

    ```html
    <script>
        var name;
        console.log(name);
    </script>
    // >undefined
    
    <script>
            console.log(name);
    </script>
    // >报错 name is not defined
    ```

    

 2. var的值可以是整型、浮点型、布尔型、字符和字符串，且初始化为某个类型后，后面的再赋值可以是别的类型

    ```html
    <script>
        var name = "pig";
        name = 18;
        console.log(name);
    </script>
    // >18
    ```

 3. 不声明，直接赋值，输出正确，但会成为全局变量

    ```html
    <script>
    	name = "pig";
        console.log(name);
    </script>
    // >pig
    ```

    

 4. 用prompt()空输入的值为null

    ```html
    <script>
        var name = "pig";
        name = prompt();
        console.log(name);
    </script>
    // 输入 ''
    // >null
    ```

---

## 8.数据类型

### 8.1 数据类型的作用

​	每种数据类型所占空间大小不同，为了充分利用空间，需要设置数据类型。



### 8.2 变量的数据类型

1. JavaScript中的==变量==属于一种弱类型（动态语言），在程序运行的过程中，类型会被自动确定。

```html
<sctript>
    var abc; // 不能确定数据类型
    var num = 10;// 程序在解析到这一行时，根据赋值号右侧的值才能确定变量类型
</sctript>
```

2. ==变量==的数据类型可变

```html
<script>
    var name = "pig";
    name = 18;
    console.log(name);
</script>
// >18
```



### 8.3 JS中的数据类型

1. 简单数据类型

Number（包含整型和浮点型）

```javascript
    var int = 10;
    var PI = 3.14;
    var num1 = 012; // 0开头的数字为八进制，转换为10进制为8
    var num2 = 0xa; //0x开头的数字为十六进制，转换为十进制为26


/* 此外还有数字型的最大值和最小值，用Number.MAX_VALUE和Number.MIN_VALUE表示
三个特殊值：Infinity，-Infinity，NAN(非数字)

  console.log(Number.MAX_VALUE * 2) > Infinity
  console.log(Number.MIN_VALUE / 2) > 0
  console.log('abcd' - 100) > NAN

isNAN() 能判断一个值是否为非数，若该值为非数，则返回true，该值为数，则返回false
console.log(isNAN('abcd')) > true
```

String：字符串型

```js
// JS中可用''或""表示字符串（推荐使用单引号），可以用''包含""，也可以用""包含''(外单内双，外双内单，还可以用\转义)
转义符：\n 换行
	\\ 反斜杠
	\" 双引号
	\' 单引号
	\t tab缩进
	\b 空格

str.length // > 字符串长度
str1 + str2 //字符串的拼接

//str与其他类型使用'+'相连，会自动把其他类型转换为字符型
'abcd' + 18 > 'abcd18'
18 + 'abcd' > '18abcd'
'12' + 12 > '1212'
'abcd' + true > 'abcdtrue'
'abcd' + undefined > 'abcdundefined'
'abcd' + null > 'abcdnull'

// 数字相加，字符相连，利用这一特性可以做到如下功能
var age = 18;
console.log('妈妈永远' + age + '岁')
age += 1;
console.log('妈妈永远' + age + '岁')
// > '妈妈永远18岁' '妈妈永远19岁'
```

Boolean：布尔型

```javascript
// 参加算术法运算时当做1/0
console.log(true + 1); //> 2
console.log(false -1) //> -1
console.log(true / 5) //> 0.2
console.log(false * 3) //>0
```

Undefined：声明但没有初始化

```javascript
var age;
console.log(age) //> Undefined
//Undefined与数字相加，最后结果是NAN
console.log(undefined + 1); // > NAN
```

Null：声明但给的是空值

```javascript
// null与数字相加，仍是原数字
console.log(null + 10); // > 10
// null与字符串相加，是字符串拼接
console.log(null + 'abcd'); // > nullabcd
```



### 8.4 获取数据类型

```javascript
// 使用typeof 变量名  可以获得该变量的类型
// 选用隐式命名，有利于代码的阅读
var num = 10;
var str = 'abcd';
var flag = true;
var vari = undefined;
var timer = null;
consolf.log(typeof num); // > number
consolf.log(typeof str); // > string
consolf.log(typeof flag); // > true
consolf.log(typeof vari); // > undefined
consolf.log(typeof timer); // > object(?)

// 可以验证prompt输入值属于字符型
var age = prompt('请输入您的年龄')；
consolf.log(typeof age); // > string
```



### 8.5 数据类型转换

1. 转成字符串

   | 方式                  | 说明                     | 案例                                    |
   | --------------------- | ------------------------ | --------------------------------------- |
   | toString()            | 生成一个字符串           | var num = 1;  alert(num.toString())     |
   | String() 强制转换     | 将非字符串转成字符串     | var num = 1;  alert(String(num))        |
   | 加号拼接字符 隐式转换 | 和字符串拼接的都是字符串 | var num = 1;  alert(num + '我是字符串') |

   ```javascript
   // num.toString()
   var num = 112;
   var str = num.toString();
   console.log(str);// > 112
   console.log(typeof str);// > string
   console.log(typeof num)// > number
   
   //String(num)
   var num1 = 112;
   var str = String(num1)
   console.log(str);// > 112
   console.log(typeof str);// > string
   console.log(typeof num1);// > number
   
   //num + ''
   // 该方法使用最多
   var num = 112;
   var str = num + '';
   console.log(str);// > 112
   console.log(typeof str);// > string
   console.log(typeof num)// > number
   ```

   

2. 转换成数值型

   | 方式                   | 说明                           | 案例                |
   | ---------------------- | ------------------------------ | ------------------- |
   | parseInt(string)函数   | 将string转换为整数数值型       | parseInt('78')      |
   | parseFloat(string)函数 | 将string类型转换成浮点数数值型 | parseFloat('78.21') |
   | Number() 强制转换函数  | 将string类型转换成数值型       | Number('78')        |
   | js 隐式转换（- * /）   | 利用算术运算隐式转换为数值型   | '12' - 0            |

   ```javascript
   var str = '123';
   var num = parseInt(str);
   console.log(num);// > 123
   console.log(typeof num);// > number
   
   var str = '12.3';
   var num = parseFloat(str);
   console.log(num);// > 12.3
   console.log(typeof num);// > number
   
   // parseInt()和parseFloat()会截取字符串首部连续的最长数字，若首部非数，则表示为NAN
   var str1 = '120px'；
   var num1 = parseInt(str1)
   var str2 = '12p0x'
   var num2 = parseInt(str2)
   var str3 = 'px120'
   var num3 = parseInt(str3)
   console.log(num1);// > 120
   console.log(num2);// >12
   console.log(num3);// > NAN
   
   //Number(num) 强制转换
   var str = '123';
   var num = Number(str);
   console.log(num);// >123
   console.log(typeof num);// >number
   
   //隐式转换 - * /
   var str1 = '12.3';
   var num1 = str - 0;
   console.log(num1);// > 12.3
   console.log(typeof num);// > number
   
   //隐式转换还可作用于两个字符串之间
   var str1 = '123'；
   var str2 = '456'
   console.log(str1 - str2);// > -333
   
   //隐式转换还有一种办法：加负号
   var str1 = '123';
   var str2 = '456';
   console.log(str1-(-str2));// > 579
   ```

3. 转换为布尔型

   | 方式          | 说明               | 案例            |
   | ------------- | ------------------ | --------------- |
   | Boolean()函数 | 其他类型转成布尔值 | Boolean('true') |
   | !! 强制转换   | 其他类型转成布尔值 | !!0             |

   代表空、否定的值都会转换成false；// 比如'' 、0 、NAN 、null 、undefined

   其余转换为true

---

## 9.标识符、保留字、关键字

标识符：指变量或函数的名字，如var number等

关键字：指语言已经使用的名称。如break、if、switch等

保留字：指还未使用但将来可能会成为关键字的名字。

以上三种均不能用作变量名

---

## 10.运算符

​	运算符(operator 操作符)，用于实现赋值、比较和执行算术运算等功能。

​	JS中常见运算符有

* 算术运算符：+ - * / %
* 自增、自减运算符：i++ i-- ++i --i，开发时大部分用后置自增
* 比较运算符：返回值为布尔型，有> < >= <= == != === !\==
* 逻辑运算符：&& || !
* 赋值运算符：=

### 10.1 浮点数精度

```javascript
var num = 0.1 + 0.2；
console.log(num); // > 0.30000000004
```

### 10.2 默认转换数据类型

```javascript
// ==会有默认转换数据类型，把字符串型的数据转换成数值型
console.log(18 == 18); // > true
console.log(18 == '18'); // > true
console.log(18 != '18');// > false
// 全等号(三个等号)===，数值和类型都相等时返回true，否则返回false
console.log(18 === 18); // > true
console.log(18 === '18'); // > false
```

### 10.3 短路运算（逻辑中断）

1.逻辑与短路运算

与(&&)运算中，当左边表达式的值是true(非false)时，就直接返回右边的表达式，如果左边为假，则直接返回左边，<span style="color:red;">右边不执行</span>

```javascript
console.log(123 && 456)； // > 456
console.log(0 && 123); // > 0
console.log('' && 123); // > ''
```

2.逻辑或短路运算

或(||)运算中，如果左边表达式为真，则返回左边，<span style="color:red;">右边不执行</span>，否则返回右边

```javascript
console.log(123 || 456); // > 123
console.log(0 || 343); // > 343
console.log(0 || ''); // > ''
```

### 10.4 运算符优先级

| 优先级 | 运算符     | 顺序           |
| ------ | ---------- | -------------- |
| 1      | 小括号     | ()             |
| 2      | 一元运算符 | ++ -- ！       |
| 3      | 算术运算符 | 先*/% 后+-     |
| 4      | 关系运算符 | > >= < <=      |
| 5      | 相等运算符 | == != === !\== |
| 6      | 逻辑运算符 | 先&& 后\|\|    |
| 7      | 赋值运算符 | =              |
| 8      | 逗号运算符 | ,              |

### 10.5 && 和 || 的特殊用法（配合短路运算）

&&：找第一个falsy的值

```javascript
// 寻找第一个falsy的值
var val0 = 0, val1 = 1, val2 = 2;
var result = val1 && val2 && val0;
console.log(result); // 0

// 配合短路运算
var f0 = () => {
    console.log("Call f0");
    return 0;
}
var f1 = () => {
    console.log("Call f1");
    return 1;
}
var f2 = () => {
    console.log("Call f2");
    return 2;
}
var result = f1() && f0() && f2(); // Call f1 // Call f0 // f2未被调用
console.log(result); // 0

// 避免一些异常
var obj = {f: void 0}
// obj.f(); // Uncaught TypeError: obj.f is not a function
obj && obj.f && obj.f(); // 未抛出异常 // 当有一段链式调用时这很有用
obj?.f?.(); //当然使用ES2020的?.操作符也可以
```

||: 寻找第一个truthy的值

```javascript
// 寻找第一个truthy的值
var val0 = 0, val1 = 1, val2 = 2;
var result = val0 || val1 || val2;
console.log(result); // 1

// 设定默认值
var v1 = void 0;
var result = val0 || 1;
console.log(result); // 1
```



---

## 11.流程控制

顺序流程（默认）、分支流程、循环流程

### 11.1 if语句

```javascript
// 1.单分支表达式：条件表达式为真，则执行大括号内的代码，为假则不执行
if(条件表达式){
    代码1
    代码2
    ...
}

// 示例，如果5 > 3，则弹出网页警示框
if (5 > 3) {
    alert("5确实是大于3的");
}
// 弹出警示框，内容是"5确实是大于3的"

// 2.双分支表达式：条件为真，执行代码1，否则执行代码2
if(条件表达式) {
    代码1
}
else {
    代码2
}
```

```javascript
// 3.if else if 语句，利用多个条件选择不同语句执行
if(条件表达式1) {
    代码1
} else if(条件表达式2) {
    代码2
} else if(条件表达式3) {
    代码3
} else {
    代码4
}
```

### 11.2 三元表达式

```javascript
// 条件表达式 ? 表达式1 : 表达式2；  条件表达式为真，返回表达式1；为假返回表达式2
// 示例：输入一个0-59的整数，大于9时输出，小于等于9时在前面补0
var num = pormpt('输入0~59之间的整数');
var outPut = num > 9 ? num+'' : '0' + num;
console.log(outPut);
```

### 11.3 switch语句

switch中各个case所对应的执行语句在内存中是连续存放的，而case仅仅是跳转到对应代码的那一行，并不规定执行的范围，因此需要break跳出，否则会一直执行下去

```javascript
// 如果switch中的表达式匹配到了case中的value，则执行该语句，如果没有匹配的，则执行default中的语句
// 如果不添加break，就会从匹配的地方一直执行下去(可能会遇到下一个break)
switch(表达式) {
    case value1:
        执行语句1;
        break;
    case value2:
        执行语句2;
        break;
    ...
    default:
        执行最后的语句;
}

// 示例：根据输入的成绩给出评价
var score = prompt('输入0~100之间的整数');
        switch(Math.floor(score/10)) {
            case 10:
                alert('C语言大佬！');
                break;
            case 9:
                alert('马萨卡，我是天才？');
                break;
            case 8:
                alert('狠狠地踩70分的头!');
                break;
            case 7:
                alert('我下面还有人垫着呢~');
                break;
            case 6:
                alert('六十分也很棒了呢！');
                break;
            default:
                alert('注意进厂时机。');
        }
```

// <u>表达式与value匹配时，必须保证值和==类型==全部一致(===)才能匹配</u>

### 11.4 循环语句

1. for循环，适合执行某些与计数有关的代码

```javascript
/* for(初始变量;循环条件;操作表达式) {
	循环体
}
*/
// 初始化变量往往作为计数器，操作表达式往往作为变量自增或自减
// 示例：若每次输出的数字会自增，可直接调用计数器作为数字输出
for(var i = 0; i < 100; i++) {
    console.log('执行' + (i+1) + '次');
}

// 让用户控制循环次数
var num = prompt("想冲多少次？");
for(var i = 0; i < num; i++) {
    console.log('冲了' + (i+1) + '次');
}

// 累加
var num = prompt("第1天，你冲了1次，第2天，你冲了2次……第n天你冲了n次，那么你想冲多少天？");
var sum = 0;
for(var i = 1; i <= num; i++) {
    sum += i;
}
console.log('天啊!' + num + '天内你冲了' + sum + '次，注意身体吧。');

// 分别求100以内的奇数和以及偶数和
var sumOfOdds = 0;
var sumOfEvens = 0;
for(var i = 2; i <= 100; i += 2) {
    sumOfOdds += i-1;
    sumOfEvens += i;
}
console.log(sumOfOdds);
console.log(sumOfEvens);

// 9x9乘法表
var str = '';      
for(var i = 1; i <= 9; i++) {
    str += '| '
    for(var j = 1; j <= i; j++) {
        str += j + 'x' + i + '=' + i*j + ' | ';
    }
    str += '\n'
}
console.log(str);
```

// 初始化变量可以为空，判断<u>循环条件</u>是每次循环==最先==执行的，<u>操作表达式</u>是每次循环==最后==执行的代码

2. while循环

```javascript
while (条件表达式) {
    代码
}

// 打印1-100内的整数
var i = 1;
while (i <= 100) {
    console.log(i);
    i++;//注意别死循环
}
```

3. do while循环

```javascript
// 先执行一次循环体，再进行条件判断
do {
    代码
}while(条件表达式)
// 至少执行一次
```

### 11.5 coutinue 与 break

1. continue:跳出本次循环，直接跳到下一次循环

```javascript
// 求除了7的整数倍以外，1-100内的整数和
var sum = 0;
for (var i = 1; i <= 100; i++) {
    if(i % 7 == 0) {
        continue;
    }
    sum += i
}
console.log(sum);
```

2. break:退出整个循环

```javascript
// 输出0-50的整数
var i = 0;
while (1) {
    console.log(i);
    if (i == 50) {
        break;
    }
}
```



---

## 12.数组

### 12.1 创建方法

1. 利用new关键字创建数组

   ```javascript
   // var 变量名 = new Array();
   var arr = new Array();
   ```

   

2. 利用数组字面量[]创建数组==常用==

   ```javascript
   //var 变量名 = [数据1, 数据2, ...];
   var arr1 = [1, 2, 'pig', true];// 可以在同一个数组内存放不同类型的数组元素
   ```



### 12.2 访问数组元素

利用索引号访问数组元素

```javascript
//arr[n],n从0开始
var arr1 = [1, 2, 'pig', true];
console.log(arr1[2]); // > 'pig'
console.log(arr1[0]); // > 1

// 访问越界会提示undefined
var arr1 = [1, 2, 'pig', true];
console.log(arr1[4]); // > undefined

// 循环遍历数组元素     arr.length: 返回数组元素的个数
var arr1 = [1, 2, 'pig', true];
for(var i = 0; i < arr1.length; i++) {
    console.log(arr1[i]);
}
```



### 12.3 新增元素（扩容）

1. 修改length长度

   ```javascript
   var arr1 = [1, 2, 'pig', true];
   arr1.length = 5; 
   console.log(arr1[4]); // > undefined
   // arr1[4]默认为undefined
   ```

2. 直接向新索引号中写入元素（自动扩容）

   ```javascript
   var arr1 = [1, 2, 'pig', true];
   arr1[4] = false;
   console.log(arr1[4]); // > false
   
   // 给数组名直接赋值，会覆盖掉数组
   var arr1 = [1, 2, 'pig', true];
   arr1 = 'abcd';
   console.log(arr1); // > 'abcd'
   
   // 示例：直接用for循环给数组增加元素
   var arr1 = [];
   for (var i =0; i < 10; i++) {
       arr1[i] = i + 1;
   }
   console.log(arr1); // > [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
   
   // 示例：将arr1中大于10的元素存到arr2中
   var arr1 = [12, 3, 4, 5, 66, 77, 45, 10];
   var arr2 = [];
   for (var i =0; i < arr1.length; i++) {
       if (arr1[i] > 10) {
           arr2[arr2.length] = arr1[i];
       }
   }
   console.log(arr2); // > [12, 66, 77, 45]
   ```

3. 使用array.push(newElement)

   ```javascript
   var arr1 = [1, 2, 'pig', true];
   arr1.push('123');
   console.log(arr1); // > [1, 2, 'pig', true, '123']
   ```



### 12.4 删除元素

1. 创建新数组，将原数组内未被删除的元素依次添加到新数组中

   ```javascript
   // 示例：将arr1中的0删除
   var arr1 = [11, 0, 2, 3, 4, 5, 0, 3, 2];
   var arr2 = [];
   for (var i = 0; i < arr1.length; i++) {
       if (arr1[i] != 0) {
           arr2[arr2.length] = arr1[i];
       }
   }
   console.log(arr2); // > [11, 2, 3, 4, 5, 3, 2]
   ```

2. 使用array.pop()

   ```javascript
   var arr1 = [1, 2, 'pig', true];
   arr1.pop();
   console.log(arr1); // > [1, 2, 'pig']
   ```

3. 使用splice()

   ```javascript
   var arr1 = [1, 2, 'pig', true];
   arr1.splice(1,1); // 删除起始位置，删除个数
   console.log(arr1); // > [1, 'pig', true]
   ```

   

### 12.5 翻转数组

1. 使用循环，将数组翻转

   ```javascript
   var arr1 = [11, 0, 2, 3, 4, 5, 0, 3, 2];
   for (var i = 0; i < parseInt(arr1.length / 2); i++) {
       var temp = arr1[i];
       arr1[i] = arr1[arr1.length - 1 - i];
       arr1[arr1.length - 1 - i] = temp;
   }
   console.log(arr1); // > [2, 3, 0, 5, 4, 3, 2, 0, 11]
   ```

2. 使用array.reverse()

   ```javascript
   var arr1 = [11, 0, 2, 3, 4, 5, 0, 3, 2];
   arr1.reverse();
   console.log(arr1); // > [2, 3, 0, 5, 4, 3, 2, 0, 11]
   ```



### 12.6 冒泡排序

```javascript
var arr1 = [1, 2, 3, 4, 5];
for (var i = arr1.length - 1; i > 0; i--) {
    for (var j = 0; j < i; j++) {
        if (arr1[j] < arr1[j + 1]) {
            var temp = arr1[j];
            arr1[j] = arr1[j + 1];
            arr1[j + 1] = temp;
        }
    }
}
console.log(arr1); // > [5, 4, 3, 2, 1]
```



## 13.函数

### 13.1 声明函数

```javascript
// 1. 命名函数：利用函数关键字自定义函数
function 函数名 (形参1, 形参2, ...) {
    代码1
    代码2
    ...
}
// 与C语言不通，形参不必声明类型，直接使用形参名
// 示例：求100以内的整数和
function getSum() {
    var sum = 0;
    for (var i = 1; i <= 100; i++) {
        sum += i;
    }
    return sum;
}

// 2. 匿名函数：函数表达式 var 变量名 = function() {}
var fun = function(形参1, 形参2, ...) {
    代码1
    ...
}
fun(实参1, 实参2, ...);
// 变量里存的是函数
// 匿名函数只在被调用时占用空间
```

### 13.2 函数调用

```javascript
// 函数名(实参1, 实参2, ...)
var sumOf100 = getSum();
console.log(sumOf100);
```

如果实参个数多于形参个数，会忽略多余的实参。
如果实参个数少于形参个数，则该变量没有接收值，结果为undefined

```javascript
function getSum(num1, num2) {
    console.log(num1 + num2);
}

getSum(1,2);// > 3
getSum(1,2,3); // > 3
getSum(1); // > NAN
```



### 13.3 函数的返回值

```javascript
// 使用return将结果返回
// 示例：求100以内的整数和
function getSum() {
    var sum = 0;
    for (var i = 1; i <= 100; i++) {
        sum += i;
    }
    return sum;
}
var sumOf100 = getSum();
console.log(sumOf100);

// 示例：返回两个数的较大值
function getMax(num1, num2) {
    return num1 > num2 ? num1 : num2;
}

// 示例：判断年份是否为闰年
function isLeapYear(year) {
    return year % 400 == 0 || year % 4 == 0 && year % 100 != 0;
}
console.log(isLeapYear(1999)); // > false
console.log(isLeapYear(2000)); // > true
```

函数执行return返回时，会终止函数

```javascript
function abc () {
    return 123;
    return 456;
}
// 123
```

return只能返回一个值，若有多个值，以最后一个为准

```javascript
function abc () {
    return 123,456;
}
// 456
```

若要返回多个数字，则以数组形式返回

```javascript
function abc () {
    return [123,456];
}
// [123,456]
```

若函数没有return，则返回值为undefined

```javascript
function abc () {

}
// undefined
```



### 13.4 arguements

内置在所有函数中，是一个==伪数组==，将所有传递过来的实参存储在数组中

伪数组：具有数组的length属性，按照索引的方式进行存储，但没有数组的一些方法（如pop()、push())

```javascript
function fn() {
    console.log(arguements);
    console.log(arguements.length);
    console.log(arguemengts[2]);
}
fn(1,2,3);
// > [1, 2, 3]
// > 3
// > 3

// 求任意个数的数值型的最大值
function getMax() {
    var max = arguements[0];
    for(var i = 1; i < arguements.length; i++) {
        if(arguements[i] > max) {
            max = arguements[i];
        }
    }
    return max;
}
```



### 13.5 函数的互相调用

```javascript
// 在fn2()中调用fn1()
function fn1() {
    代码
}
function fn2() {
    fn1();
}
fn2();

// 示例：返回某年二月份天数  在backFebDays()中调用isLeapYear()
function backFebDays() {
    var year = prompt('请输入年份');
    if(isLeapYear(year)) {
        alert('当前年份是闰年，2月有29天');
    } else {
        alert('当前年份是平年，2月有28天');
    }
}
function isLeapYear(year) {
    return year % 400 == 0 || year % 4 == 0 && year % 100 != 0;
}
```



## 14.作用域

​	代码或变量起作用的范围。作用域可以提高程序可靠性，减少命名冲突。

### 14.1 JS的作用域（es6之前）

1.全局作用域

​	整个script标签，或是一个单独的js文件

```html
<script>
    var num = 10;
    // 全局作用域
</script>
```



2.局部作用域(函数作用域)

​	在函数内部定义的变量，只能在函数内部起效果和作用。

```javascript
function fn() {
    var num = 10;
    // 局部作用域
}
```



### 14.2 全局变量与局部变量

全局变量：作用域为全局的变量

局部变量：作用域为局部（函数内部）的变量

在script标签下定义的变量，或在==函数==中使用==变量名==直接定义的变量都是全局变量。

```javascript
// <scrpit>
var num1 = 10;// 全局变量
function fn1() {
    var num1 = 20;// 局部变量
    num3 = 20;// 全局变量
}
console.log(num1);// > 10
console.log(num2);// > 20
```

从执行效率来看全局变量和局部变量：

(1) 全局变量只有浏览器关闭时才会销毁，比较站内存资源；

(2) 局部变量 当程序执行完毕就会销毁，比较节约内存资源；



### 14.3 块级作用域{}

​	用{}包裹的作用域被称为块级作用域，在ES6版本后更新。



### 14.4 作用域链

​	==内部函数==可以访问==外部函数==的机制

​	链式查找：内部函数访问外部函数的方式（就近原则），先查找自身作用域，再逐级向外层查找

```javascript
// JS中函数可以嵌套定义
var num = 10;
function fn() {
    var num = 20;
    function fn1() {
        console.log(num);
    }
    fn1();
}
fn(); // > 20
```



## 15 预解析

​	JavaScript引擎运行时，先进行==预解析==，之后==代码执行==。

1. 预解析：js引擎会把js中所有 var 还有 function 提升到当前作用域最前面、
2. 代码执行：代码按照书写顺序从上往下执行。

### 15.1 预解析

​	预解析分为变量预解析（变量提升）和函数与解析（函数提升）。

1. 变量提升/函数提升：把所有变量/函数声明提升到当前作用域最前面，不提升赋值操作。

   函数/变量调用必须写在函数/变量声明下面。

```javascript
fun();
var fun = function() {
    console.log(22);
}

// 相当于
var fun；
fun();
fun = function() {
	console.log(22);
}
// 不能执行

fun();
function fun() {
    console.log(22);
}

// 相当于
function fun() {
    console.log(22);
}
fun();
// 能执行
```

```javascript
// 一道经典面试题,但ES6之后失效了
fn();
console.log(c);
console.log(b);
console.log(a);
function fn() {
    var a = b = c = 9;// ES6之前，这段代码表示var a = 9; b = 9; c = 9; ES6之后表示var a = 9, b = 9, c = 9;
    console.log(a);
    console.log(b);
    console.log(c);
}
```



## 16.对象

​	对象是一组无序的相关==属性==和==方法==的集合。

### 16.1 创建对象的三种方法

1. 利用字面量：{}

   ```javascript
   var obj = {}; // 创建了一个空对象
   var obj = {
       uname: '张三疯', // 属性名: 属性值,
       age: 18,
       sex: '男',
       sayHi: function() {
           console.log('hi~');
       } // 方法: function() {}
   }
   // 一定注意多个属性和方法用冒号表示，用逗号隔开，方法冒号后跟匿名函数
   ```

   

2. 利用new object

   ```javascript
   var obj = new Object(); // 创建一个空对象
   // 用赋值的方法为对象添加属性
   obj.uname = '张三疯';
   obj.age = 18；
   obj.sex = '男';
   obj.sayHi = function() {
       console.log('hi~')
   }
   ```

   

3. 利用构造函数==重要==

   ```javascript
   // 利用函数的方法创建同一类对象，将相同的属性和方法抽象出来封装到函数里
   function 构造函数名() {
       this.属性 = 值;
       this.方法 = function () {}
   }
   // 规范：构造函数名首字母必须大写
   // 示例：
   function Star(uname, age, sex, song) {
       this.uname = uname;
       this.age = age;
       this.sex = sex;
       this.sing = function() {
           console.log(song);
       }
   }
   // 构造函数不需要 return 就能返回结果
   // 创建对象
   var ldh = new Star('刘德华', 18, '男');
   console.log(ldh.age);
   ```

   new在执行时会做四件事情：

   1. 在内存中创建一个新的空对象。
   2. 让this指向这个新的对象。
   3. 执行构造函数里面的代码，给这个新对象添加属性和方法。
   4. 返回这个新对象（所以不需要添加return）。

### 16.2 调用对象属性

```javascript
// 1. 对象名.属性名
console.log(obj.uname); // > '张三疯'

// 2. 对象名['属性名']
console.log(obj['age']); // > 18
```



### 16.3 调用对象方法

```javascript
// 对象名.方法名()
obj.sayHi(); // > 'hi~'
```



### 16.4 遍历对象的属性

```javascript
// 使用for in，一般使用var k作为遍历变量
for (var k in ldh) {
    console.log(k);// k表示属性名/方法名
    console.log(ldh[k]);// obj[k]表示属性值/方法值
}
```



## 17.JS内置对象

​	JS中的对象分为3种：自定义对象、内置对象、浏览器对象

​	前两种是JS基础内容，属于ECMAScript；第三个属于JS独有

​	内置对象就是JS自带的对象，具有一定的基本属性和方法。

​	有Math、Date、Array、String等。

​	可以在[Web 开发者指南 | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/Guide#javascript)中查询

### 17.1 Math对象

​	Math数学对象不是一个构造函数，不需要用new来调用，直接使用里面的属性和方法即可

```javascript
console.log(Math.PI); // > 圆周率
console.log(Math.max(1,99,3)); // > 99
Math.PI // 圆周率
Math.max() // 取最大值
Math.min() // 取最小值
Math.floor() // 向下取整 parseInt()也是向下取整 
Math.round() // 四舍五入取整
Math.ceil() // 向上取整
Math.abs() // 取绝对值
Math.random() // 返回一个在[0,1)内的随机数

// 封装一个自己的myMath对象
var myMath = {
    PI: 3.1415926535,
    max: function () {
        var max = -Infinity;
        for (var i = 0; i <= arguments.length - 1; i++) {
            if (arguments[i] > max) {
                max = arguments[i];
            }
        }
        return max;
    }, // 注意逗号
    min: function () {
        var min = Infinity;
        for (var i = 0; i <= arguments.length - 1; i++) {
            if (arguments[i] < min) {
                min = arguments[i];
            }
        }
        return min;
    }
}
console.log(myMath.PI);
console.log(myMath.max(1, 2, 3, 4));
console.log(myMath.min(1, 2, 3, 4));
```



### 17.2 Math.random()

```javascript
Math.random() // 返回一个在[0,1)内的随机数

//返回一个[min,max)之间的随机整数
function getRandomInt(min, max) {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random()*（max-min)）+min;
}

// 返回[min, max]之间的随机整数，min和max都是整数
function getRandomInt(min, max) {
    return Math.floor(Math.random() *(max - min + 1))+ min;
}
```



### 17.3 Data日期对象的使用

```javascript
// Date() 是一个构造函数，必须使用new来调用创建日期对象
var date = new Date(); 
console.log(date);// 没有参数时，返回即时日期和时间

// 数字型参数 年, 月, 日, 时, 分, 秒, 毫秒
var date = new Date(2019, 10);
console.log(date); // > 会返回2019年11月，月份从0开始计，范围是0~11。当至少提供了年和月时，会将其他值默认取最小

// 字符串型参数
var date = new Date('2019-10-5 10:30:40');
console.log(date);// > 会返回2019年10月5日

// 日期格式化，分别得到年、月、日、时、分、秒、星期几
function getDay(day) {
    switch (day) {
        case 0:
            return '星期日';
        case 1:
            return '星期一';
        case 2:
            return '星期二';
        case 3:
            return '星期三';
        case 4:
            return '星期四';
        case 5:
            return '星期五';
        case 6:
            return '星期六';
    }
}

var arrDays = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'];//另一种星期的转换方法
var date = new Date();
var year = date.getFullYear();
var month = date.getMonth() + 1;
var day = date.getDate();
var hour = date.getHours();
var minute = date.getMinutes();
var second = date.getSeconds();
var getDay = array[date.getDay()];
alert('现在是' + year + '年' + month + '月' + day + '日 ' + hour + '时' + minute + '分' + second + '秒' + '，今天是' + getDay);
```



### 17.4 获得时间戳

```javascript
// 时间戳：距离1970年1月1日 00:00:00 的毫秒数
// 创建Date对象
var date = new Date();
console.log(date.valueOf());
console.log(date.getTime());

// 简单的写法
var date1 = +new Date(); // +new Date() 返回的是时间戳
console.log(date1);

// H5新增 获得总毫秒数
console.log(Date.now());
```

制作一个倒计时

```javascript
function countdown(time) {
    var immediateTime = +new Date();
    var inputTime = +new Date(time);
    var timeDif = inputTime - immediateTime;
    var allSeconds = parseInt(timeDif / 1000);
    var seconds = parseInt(allSeconds % 60);
    seconds = seconds < 10 ? '0' + seconds : seconds;
    var minutes = parseInt(allSeconds / 60 % 60);
    minutes = minutes < 10 ? '0' + minutes : minutes;
    var hours = parseInt(allSeconds / 60 / 60 % 24);
    hours = hours < 10 ? '0' + hours : hours;
    return '倒计时 ' + hours + ':' + minutes + ':' + seconds;
}
```

### 17.5 数组对象

```javascript
// 创建一个空数组
var arr = new Array(2);// 表示数组长度为2，有两个空元素
var arr1 = new Array(2,3);// 表示创建数组[2, 3]

// instanceof 能检测某个对象是否属于某个类
// 示例：
function Star(uname, age, sex, song) {
    this.uname = uname;
    this.age = age;
    this.sex = sex;
    this.song = function () {
        console.log(song);
    }
}
var ldh = new Star('刘德华', 18, '男', '冰雨');
console.log(ldh instanceof Star);// > true

// 检测输入值是否为数组
function (arr) {
    if (arr instanceof Array) {
        ...
    }
    return 'error，参数必须为数组';
}
    
// Array.isArray() ie9以上支持
arr.isArray(); // > true
obj.isArray(); // > false
```



### 17.6 添加或删除数组元素的方法

| 方法                             | 效果                       | 返回值         |
| -------------------------------- | -------------------------- | -------------- |
| array.push(elem1, elem2, ...)    | 在数组末尾添加元素         | 返回数组长度   |
| array.pop()                      | 删除数组末尾的元素，无参数 | 返回被删除元素 |
| array.unshift(elem1, elem2, ...) | 在数组开头添加元素         | 返回数组长度   |
| array.shift()                    | 删除数组开头的元素，无参数 | 返回被删除元素 |



### 17.8 数组的其他操作

1. 数组翻转

   array.reverse()

   ```javascript
   var arr = [1, 2, 3];
   arr.reverse();
   console.log(arr);// > [1, 2, 3]
   ```



2. 数组排序

   array.sort();// 字典排序，先比较最左边的数

   ```javascript
   var arr = [13, 4, 77, 1, 7];
   arr.sort();
   console.log(arr);// > [1, 13, 4, 7, 77]
   
   
   
   
   arr.sort(function(a, b) {
       return a - b;// 升序排列
   })；
   console.log(arr); // > [1, 4, 7, 13, 77]
   
   
   
   arr.sort(function(a, b) {
       return b - a;// 降序排列
   });
   console.log(arr); // > [77, 13, 7, 4, 1]
   ```

3. 数组索引

   ```javascript
   // arr.indexOf(elem) 查找元素在数组中位置，只返回第一个满足条件的索引号
   var arr = ['red', 'green', 'bule', 'red', 'pink']
   console.log(arr.indexOf('red')); // > 0
   
   // arr.lastIndexOf(elem) 查找元素在数组中位置，只返回最后一个满足条件的索引号
   console.log(arr.lastIndexOf('red')); // > 3
   
   // 若找不到，则返回-1
   console.log(arr.indexOf('skyblue')); // > -1
   
   ```

4. 数组去重

   ```javascript
   function unique(arr) {
       var newArr = [];
       for (var i = 0; i < arr.length; i++) {
           if (newArr.indexOf(arr[i]) == -1) {
               newArr.push(arr[i]);
           }
       }
       return newArr;
   }
   ```

5. 数组转化为字符串

   ```javascript
   // 1. arr.toString()
   var arr = [1, 2, 3];
   console.log(arr.toString()); // > '1,2,3'
   
   // 2. arr.join(分隔符)
   var arr = [1, 2, 3];
   console.log(arr.join('|')) // > '1|2|3'
   ```



6. 连接两个数组

   ```javascript
   // arr1.concat(arr2, arr3, ...) , 返回值为连接后的新数组，对原数组无影响
   var arr1 = [1, 2, 3];
   var arr2 = [4, 5, 6];
   var arr3 = [7, 8, 9]
   var arr4 = arr1.concat(arr2, arr3);
   console.log(arr1); // > [1, 2, 3]
   console.log(arr2); // > [4, 5, 6]
   console.log(arr3); // > [7, 8, 9]
   console.log(arr4); // > [1, 2, 3, 4, 5, 6, 7, 8, 9]
   ```



7. 截取数组

   ```javascript
   // arr.slice(开始索引，结束索引); 返回值为被截取元素组成的新数组，对原数组无影响
   // 结束索引取不到，实际上所能取到的元素为[arr[开始索引], ... , arr[结束索引-1]]
   // 无参数时，默认截取整个数组
   var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
   var newArr = arr.slice(1, 3);
   console.log(newArr);// > [1, 2, 3]
   console.log(arr);// > [1, 2, 3, 4, 5, 6, 7, 8, 9]
   
   // 若不指定结束索引，则默认将后面全部截取
   var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
   var newArr = arr.slice(7);
   console.log(newArr); // > [8, 9]
   
   // 负数索引代表倒数第几个
   var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
   var newArr = arr.slice(5, -2);
   console.log(newArr); // > [6, 7]
   
   // 若开始索引不大于结束索引，则截取的数组为空数组
   var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
   var newArr = arr.slice(5, 4);
   console.log(newArr); // > []
   ```



8. 数组删除

   ```javascript
   // arr.splice(被删除的起始索引, 要被删除的个数); 返回值为被删除元素组成的新数组，对原数组有影响
   var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
   var newArr = arr.splice(3, 4);
   console.log(arr);// > [1, 2, 3, 8, 9]
   console.log(newArr);// > [4, 5, 6, 7]
   
   // arr.splice(被删除的起始索引, 要被删除的个数, item1, item2, ...); splice还能将新元素(item1，item2,...)从被删除起始索引处添加进数组
   var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
   var newArr = arr.splice(3, 4, 123, 4567);
   console.log(arr); // > [1, 2, 3, 123, 4567, 8, 9]
   console.log(newArr); // > [4, 5, 6, 7]
   ```

   

### 17.9 字符串对象

基本包装类型：把简单数据类型包装成复杂数据类型。包括String、Number、Boolean

JS将基本数据类型包装成了复杂数据类型String

```javascript
var str = 'andy';

//相当于
// 1.生成临时变量
var temp = new String('andy');
// 2.赋值给声明变量
str = temp;
// 3.销毁临时变量
temp - null;
```

#### 17.9.1 字符串不可变

​	字符串内的值不变，字符串重新赋值或拼接，实际上是开辟新的空间，将指针指向该新空间。

​	不要大量==修改、拼接==字符串

​	字符串的所有方法，都不会修改字符串本身（字符串本身不可变），操作完成会返回一个新的字符串。

#### 17.9.2 根据字符返回位置

```javascript
// str.indexOf('要查找的字符', 起始的索引)  str.lastIndexOf('要查找的字符', 起始的索引)
var str = '风雨送春归，飞雪迎春到';
var index1 = str.indexOf('春');
var index2 = str.indexOf('春', 4);
console.log(index1); // > 3
console.log(index2); // > 9

// 返回字符中'o'出现的位置和次数
var str = 'abcoedoxyozzoppo';
var index = str.indexOf('o');
var position = [];
var count = 0;
while (index != -1) {
    position.push(index);
    count++;
    index = str.indexOf('o', index + 1);
}
console.log(position);
console.log(count);
```



#### 17.9.3 根据位置返回字符

| 方法名            | 说明                                 | 使用                            |
| ----------------- | ------------------------------------ | ------------------------------- |
| charAt(index)     | 返回指定位置的字符(index索引号)      | str.charAt(0)                   |
| charCodeAt(index) | 获取指定位置处的ASCII码(index索引号) | str.charCodeAt(0)               |
| str[index]        | 获取指定位置字符                     | HTML5，IE8+支持，和charAt()等效 |

```javascript
// 查找字符串中各个字符出现的次数
var o = {}
for (var i = 0; i < str.length; i++) {
    var chars = str.charAt(i);
    if (o[chars]) {
        o[chars]++;
    } else {
        o[chars] = 1;
    }
}
// console.log(o);
var max = -Infinity;
var ch = '';
for (var k in o) {
    if (o[k] > max) {
        max = o[k];
        ch = k;
    }
}
console.log(max);
console.log(ch);
```

#### 17.9.4 字符串操作方法

| 方法名                              | 说明                                                         |
| ----------------------------------- | ------------------------------------------------------------ |
| newStr = str1.concat(str2,str3,...) | 用于连接多个字符串，等效于+，+更常用                         |
| substr(start, length)               | 从start(索引号)开始，length指取的个数                        |
| slice(start,end)                    | 从start开始，截取到end之前的一个(都是索引号)，负值为倒数第几个 |
| substring(start,end)                | 从start开始，截取到end之前的一个，不接受负值                 |

建议用substring代替substr

#### 17.9.5 字符串替换

str.replace('被替换的字符串', '替换为的字符串'); 只会替换第一个字符串

```javascript
// 将字符串中所有'o'替换为'*'
var str = 'abcoedoxyozzoppo';
while(str.indexOf('o') !== -1) {
    str.replace('o', '*');
}
console.log(str); // > 'abc*ed*xy*zz*pp*'
```

#### 17.9.6 字符串转数组

```javascript
// str.split('分隔符')  区别于数组方法的join，将数组转换为字符串
var str = 'red, pink, blue';
console.log(str.split(', ')); // > ['red', 'pink', 'blue']
```

#### 17.9.7 字符串转换大小写

str.toUpperCase()

str.toLowerCase()

```javascript
var str = 'abc';
str.toUpperCase();
console.log(str);// > 'ABC'
str.toLowerCase();
console.log(str); // > 'abc'
```



---

## 18.数据类型内存分配

### 18.1 简单数据类型与复杂数据类型

​	简单数据类型：也称为<span style="color:red;">值类型</span>，有string, number, boolean, undefined, null

​	null的类型为一个空对象，因此以后想创建一个空对象，直接赋值为null

```javascript
var obj = null;
console.log(typeof obj); // > object
```

​	复杂数据类型：又称<span style="color:red;">引用类型</span>，在存储变量中存储的仅仅是地址（引用）。

​	通过new关键字创建对象，如Object、Array、Date等

​	简单数据类型都存储在==栈==中，复杂数据类型都存在==堆==中，在栈中存放对应地址。

​	栈：操作系统自动分配释放存放函数的参数值、局部变量的值等。

​	堆：一般由程序员分配释放，若程序员不释放，则由垃圾回收机制回收。



### 18.2 简单数据类型传参

​	简单数据类型传参为<span style="color:red;">值传递</span>，不会改变外层变量的值

```javascript
function fn(a) {
    a++;
    console.log(a);
}
var x = 10;
fn(x);// > 11
console.log(x);// > 10
```

​	复杂数据类型传参为<span style="color:red;">地址传递</span>，会改变外层变量的值

​	实际上是把栈内的地址复制一份进行传参。

```javascript
function Person(name) {
    this.name = name;
}
function f1(x) {
    console.log(x.name);// > 刘德华
    x.name = '张学友';
    console.log(x.name);// > 张学友
}
var p = new Person('刘德华');
console.log(p.name);// > 刘德华
f1(p);
console.log(p.name);// > 张学友
```



---

## 19.Web APIS

### 19.1 Web APIS 和 JS 关联性

​	Web APIS 包括 DOM 和 BOM，是 JS 的应用。本阶段主要学习页面交互效果。

​	API(Application Programming Interface，应用程序编程接口)：是一些预先定义的函数，提供应用程序基于某软件或硬件访问一组==例程==的能力。实现功能的接口。

​	Web API：浏览器提供的操作==浏览器功能==(BOM)和==页面元素==(DOM)的API。针对浏览器提供的接口。

​	Web API一般都有输入和输出（函数的传参和返回值），Web API很多都是方法（函数）



---

## 20.DOM

​	文档对象模型(Document Object Model)，W3C组织推荐处理可扩展标记语言(HTML或XML)的标准接口。

​	通过DOM可以改变网页内容、结构和样式。

### 20.1 DOM树

![image-20230203203413038](C:\Users\PC\AppData\Roaming\Typora\typora-user-images\image-20230203203413038.png)

​	文档(document)：一个页面就是一个文档

​	元素(element)：页面中所有标签都是元素

​	节点（node）：网页中所有内容都是节点(标签、属性、文本、注释等)

​	DOM把以上都看作对象。



### 20.2 获取元素

1. 根据ID获取

   getElementById()方法可以获取带有ID的元素对象

   ```html
   var element = document.getElementById(id); // id是一个大小写敏感的字符串，返回一个匹配到ID的DOM的Element对象，若没找到则返回null
   
   /* 文档页面从上往下加载，因此script标签要写在对应元素的下面 */
   <div id = 'time'>2019-9-9</div>
   <script>
       var timer = document.getElementById('time'); // 注意id是字符串
       console.log(timer); // > <div id = 'time'>2019-9-9</div>
       console.log(typeof timer); // > Object
       // console.dir 打印我们返回的元素对象 更好查看里面的属性和方法
       console.dir(timer);
   </script>
   ```

   

2.根据标签名获取

​	getElementsByTagName() 返回带有标签名的对象的集合

```html
var elements = document.getElementsByTagName('TagName'); // 返回的是符合标签名组成集合的伪数组
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
</ul>
<ol id = 'o1'>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
</ol>

<script>
    var lis = document.getElementByTagName('li');
    console.log(lis); // > HTMLCollection[li x 5]
    console.log(lis[0]); // > <li>1</li>
    // 只有一个li，返回的依然是伪数组形式
	// 如果没有对应元素，则返回空的伪数组

	/* 要获取某个元素（父元素）内部指定标签的子元素，还可以用
	element.getElementsByTagName('标签名'); */
    // 父元素必须是指定的单个元素，推荐使用ID获取
    var ol = document.getElementById('o1');
    console.log(ol.document.getElementsByTagName('li')); // > HTMLCollection[li x 5]
</script>
```



3. 根据类名获取(H5新增方法)

   getElementsByClassName(); // 根据类名返回元素对象集合

   ```html
   <div class = 'box'></div>
   <div class = 'box'></div>
   <div id = 'nav'></div>
   <script>
       var boxes = document.getElementsByClassName('box');
       console.log(boxes); // > HTMLCollection[div x 2]
   </script>
   ```

   



4. 根据指定选择器返回

   document.querySelector('选择器'); // 返回指定选择器的第一个元素对象

   ```html
   <div class = 'box'></div>
   <div class = 'box'></div>
   <div id = 'nav'></div>
   <ul>
       <li></li>
   </ul>
   <script>
       var box = document.querySelector('.box');
       console.log(box); // > <div class = 'box'></div>
       var nav = document.querySelector('#nav');
       console.log(nav); // > <div id = 'nav'></div>
       var li = document.querySelector('li');
       // 或var li = document.querySelector('ul').querySelector('li');
       console.log(li); // > <li></li>
   </script>
   
   
   ```
   
   document.querySelectorAll('选择器'); // 返回指定选择器的所有对象(伪数组)
   
   ```html
   <div class = 'box'></div>
   <div class = 'box'></div>
   <div id = 'nav'></div>
   <ul>
       <li></li>
       <li></li>
       <li></li>
   </ul>
   <script>
       var boxes = document.querySelectorAll('.box');
       console.log(boxes); // > HTMLCollection[div x 2]
       var lis = document.querySelectorAll('li');
       console.log(lis); // > HTMLCollection[li x 3]
   </script>
   ```



5. 获取body和html元素

   ```javascript
   var bodyEle = document.body;
   console.log(bodyEle); // > <body></body>
   
   var htmlEle = document.documentElement;
   console.log(htmlEle); // > <html></html>
   ```

   

### 20.3 事件基础

​	事件：可以被JS检测到的行为，如点击、悬停

​	简单理解：除法——响应机制

​	事件三要素：事件源、事件类型、事件处理程序		

```html
// （1）事件源：事件被触发的对象 按钮button

<button id = 'btn'>唐伯虎</button>
<script>
    var btn = document.getElementById('btn');
    // (2)事件类型 如何触发，什么事件 鼠标点击(onclick)
    // (3)事件处理程序 通过一个函数完成
    btn.onclick = function() {
        alert('点秋香');
    }
</script>
```

​	执行事件的步骤：1.获取事件源 2.注册事件（绑定事件） 3.添加事件处理程序(采取函数赋值形式)



### 20.4 常见的鼠标事件

| 鼠标事件    | 触发条件         |
| ----------- | ---------------- |
| onclick     | 鼠标左键点击     |
| onmouseover | 鼠标经过触发     |
| onmouseout  | 鼠标离开触发     |
| onfocus     | 获得鼠标焦点触发 |
| onblur      | 失去鼠标焦点触发 |
| onmousemove | 鼠标移动触发     |
| onmouseup   | 鼠标弹起触发     |
| onmousedown | 鼠标按下触发     |



### 20.5 操作元素

1. 改变元素内容

   ```html
   // element.innerText 去掉所有内容，包括空格和换行
   // element.innerHTML 去掉全部内容，保留空格和换行
   <button>显示当前系统时间</button>
   <div>某个时间</div>
   <script>
       var button = document.querySelector('button');
       var div = document.querySelector('div');
       button.onclick = function() {
           var arrDays = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'];//另一种星期的转换方法
           var date = new Date();
           var year = date.getFullYear();
           var month = date.getMonth() + 1;
           var day = date.getDate();
           var hour = date.getHours();
           var minute = date.getMinutes();
           var second = date.getSeconds();
           var getDay = arrDays[date.getDay()];
           div.innerText = '现在是' + year + '年' + month + '月' + day + '日 ' + hour + '时' + minute + '分' + second + '秒' + '，今天是' + getDay;	
       }
   </script>
   ```



2. innerText和innerHTML的区别

   ```javascript
   innerText不识别html标签，一切以字符处理
   innerHTML识别html标签，并且保留空格和换行(W3C推荐标准)
   /* <div>
           123
           <span>456</span>
      </div>
   */
   
   var div = document.querySelector('div');
   console.log(div.innerText); // > 123 456
   console.log(div.innerHTML); 
   /* >    123
   		<span>456</span>
   */
   
   // div.innerText = <span>789</span>;
   // 显示 '<span>789</span>'
   //div.innerHTML = <span>789</span>;
   // 显示 789
   ```

   

3. 修改元素属性

   ```html
   /* 常用元素的属性操作 */
   innerText、innerHTML
   src、href
   id、alt、title
   
   表单元素：type、value、checked、selected、disabled
   
   // 禁用按钮
   btn.disabled = true;
   
   btn.onclick = function() {
   	this.disabled; // this指向事件函数的调用者btn
   }
   ```



4. 修改样式属性

   ```javascript
   // 1.element.style 行内样式操作
   // 2.element.className 类名样式操作
   // 会修改行内样式，权重较高
   
   div.onclick = function() {
       this.style.backgroundColor = 'purple';
       this.style.width = '250px';
       this.style.fontSize = '14px';
   }
   ```



5. 显示和隐藏元素

   ```javascript
   btn.onclick = function() {
       box.style.display = 'none';
   }
   ```



6. 精灵图与for循环

   ```html
   <ul>
       <li></li>
       <li></li>
       <li></li>
       <li></li>
       <li></li>
       <li></li>
   </ul>
   
   <script>
       var lis = document.querySelectorAll('li');
       for (var i = 0; i < lis.length; i++) {
           lis[i].style.backgroundPosition = '0 ' + (-44*i) + 'px';
       }
   </script>
   ```

   

7. 显示文本框的隐藏内容

   ```html
   // 要用到两个鼠标事件：onfocus 获得焦点 onblur 失去焦点
   <input type = 'text' value = '手机'>
   <script>
       var text = document.querySelector('input');
       text.onfocus = function() {
           if(this.value === '手机') {
               this.value = '';
           }
           // 获得焦点时将字体颜色变黑
           this.style.color = '#333';
       }
       text.onblur = function() {
           if(this.value === '') {
               this.value = '手机';
           }
           // 失去焦点时恢复字体颜色
           this.style.color = '#999';
       }
   </script>  
   ```



8. 通过className改变样式

   ```html
   // className 会覆盖原有类名
   <style>
       div {
           width: 200px;
           height: 300px;
           background-color: pink;
       }
       .change {
           background-color: purple;
       }
   </style>
   
   <div></div>
   
   <script>
       var test = document.querySelector('div');
       test.onclick = function() {
           this.className = 'change';
           // 若不想覆盖原有类名，则可以使用this.className += ' change';
       }
   </script>
   ```

   

### 20.6 排他思想

```html
// 对一系列元素中的某一个单独作用时，将其他元素还原
    <script>
        var lis = document.querySelectorAll('li');
        var divs = document.querySelector('.outer').querySelectorAll('div');
        for (var i = 0; i < lis.length; i++) {
            lis[i].index = i;
            lis[i].onclick = function (i) {
                for (var j = 0; j < lis.length; j++) {
                    lis[j].className = "";
                }
                this.className = 'selected_li';
                for (var k = 0; k < divs.length; k++) {
                    divs[k].className = "inner";
                }
                divs[this.index].className = "inner selected_div";
            }
        }
    </script>
</body>

</html>
```



### 20.7 百度换肤

```javascript
for(var i = 0; i < imgs.length; i++) {
    imgs[i].onclick = function() {
        document.body.style.backgroundImage = 'url(' + this.src + ')'
    }
}
```



### 20.8 获取属性值

自定义属性的作用：

​	保存数据

h5规定：自定义属性名必须以'data-'开头并赋值

```javascript
1. element.属性名  //不能获取自定义属性

2. element.getAttribute('属性名')  //可以获取自定义属性，用setAttribute()设置的自定义属性必须通过getAttribute()获得

3. element.dataset.属性名
	或 element.dataset['属性名']// dataset是一个集合，存放了所有以data-开头的自定义属性

/* 自定义属性中有多个-连接的属性，比如date-list-name
	获取时要用驼峰命名法写属性名，比如element.dataset.listName
```



### 20.9 设置自定义属性

```javascript
1. element.属性名 = 属性值;  //不能设置自定义属性

2. element.setAttribute('属性名', 属性值) //设置的自定义属性在调试中可见
```



### 20.10 移除自定义属性

```javascript
element.removeAttribute('属性名');
```



### 20.11 节点操作

​	利用节点关系获取元素，逻辑性强，兼容性较差

​	元素节点：nodeType为1

​	属性节点：nodeType为2

​	文本节点：nodeType为3

开发中主要操作元素节点

1. 节点层级

   父级节点：node.parentNode ，找不到父结点就返回null

   子级节点：<del>node.childNodes（标准） ，返回一个子节点的集合，包括文本节点（换行、空格等），不推荐使用</del>

​			node.children (非标准) ，返回子元素节点的集合，开发常用

​			<del>node.firstChild , 返回第一个子节点 （包括文本）</del>

​			<del>node.lastChild ， 返回最后一个子节点 （包括文本）</del>

​			node.firstElementChild , 返回第一个子元素节点 IE9以上试用，推荐使用node.children[0]代替

​			node.lastElementChild , 返回最后一个子元素节点  推荐使用node.children[node.children.length-1]代替

​	兄弟节点：node.previousSibling 返回上一个兄弟节点（包括文本）

​			node.nextSibling 返回下一个兄弟节点（包括文本）

​			node.nextElementSibling 返回下一个兄弟元素节点 IE9以上支持

​			node.previousElementSibling 返回上一个兄弟元素节点

2. 创建节点：document.createElement('tagName'),tagName是HTML元素，创建了原先不存在的节点，也称为动态创建节点

   ​		node.appendChild(Child) 将child添加为node的==最后一个==子元素

   ​		node.insertBefore(Child, 指定元素) 将child添加为指定元素的==前一个==同级元素

   ​			可以改变已有元素的位置

3. 删除节点：node.removeChild(child); 删除node的一个子节点，并返回该子节点

4. 复制节点：node.cloneNode(); 返回一个该节点的副本

   ​		参数为空或者false，则是==浅拷贝==，只复制标签，不复制内容

   ​		参数为true，则为==深拷贝==，复制标签和内容



### 20.12 三种动态创建元素

1. document.write() // 页面重绘，会清除已加载的元素

   ```javascript
   var div = document.write('<div>123</div>'); 
   // 如果页面文档流加载完毕，再调用这句话会导致页面重绘
   ```

2. innerHTML = 'tag'

3. document.createElement('tagName')

   两者在创建大量元素时，innerHTML由于拼接字符串效率较低

   innerHTML采取数组拼接的方式，创建多个元素效率最高，但是空间复杂度较高

---



## 21.事件

### 21.1 注册事件

​	注册事件：给元素添加事件，又称绑定事件

​	注册事件的方式有两种：==传统方式==、==方法监听注册方式==

1. 传统注册方式：利用on开头的事件（onclick）

​	特点：注册事件的唯一性，同一个元素同一个事件==只能设置一个处理函数==

2. 方法监听注册方式：addEventListener()

   IE9以前不支持，使用attchEvent()代替

   同一个元素同一个时间可注册多个监听器

   按注册顺序依次执行

   ```javascript
   eventTarget.addEventListener(type, listener[, useCapture])
   // type: 事件类型，不带on，如'click'
   // listener：事件处理程序（监听器）
   // useCapture：可选
   ```

   ```javascript
   eventTarget.attachEvent(eventNameWithOn, callback) // ie9以前版本支持，现在请勿使用
   // eventNameWithOn：事件名带on，如'oncilck'，'onmouseover'
   // callback：事件处理函数
   ```

   

### 20.2 删除事件

```javascript
// 传统删除事件 eventTarget.type = null;
button.onclick = function() {
    alert('提示信息');
    button.onclick = null;
}

// 移除方法监听 eventTarget.removeEventListener(type, listener[, useCapture]);
function fn() {
    alert('提示信息');
    button.removeEventListener('click', fn);
}
button.addEventListener('click', fn)

// attachEvent的解绑 eventTarget.detachEvent(eventNameWithOn, callback)
function fn1() {
    alert('提示信息')；
    buton.detachEvent('onclick', fn1);
}
buttoon.attachEvent('onclick', fn1);
```

### 20.3 DOM事件流

​	![image-20230207174755186](C:\Users\PC\AppData\Roaming\Typora\typora-user-images\image-20230207174755186.png)

捕获阶段：先执行外层事件，再执行里层事件

冒泡阶段：先执行里层事件，再执行外层事件

JS代码中只能执行捕获或者冒泡其中一个阶段

onclick和attachEvent只能得到冒泡阶段

addEventListener(type,listener[, useCapture])第三个参数如果是true，表示事件捕获阶段调用事件处理程序。如果是false，表示冒泡阶段调用事件处理程序

<span style='color:red'>一般工作中关注事件冒泡</span>

onblur,onfocus,onmouseover,onmouseleave没有冒泡



### 20.4 事件对象

```javascript
div.onclick = function(event) {
    event = event || window.event;
    console.log(event)
} // event就是一个事件对象，写侦听的函数.通常写evt或者e
// 事件对象只有有了事件才会存在，它是系统自动创建的，不需要传递参数
// 事件对象是事件的一系列相关数据集合，包含鼠标、键盘事件的相关信息
// 事件对象也有兼容性问题，ie678通过 window.event获得事件对象
```

事件对象有很多属性和方法

1. e.target 返回触发事件的对象

   ```javascript
   div.onclick = function(e) {
       console.log(e.target) // > <div></div>
   }
   // 与this不同，this返回的是绑定事件的对象，target返回的是触发事件的对象
   ul.onclick = function(e) {
       console.log(this); // > ul
       console.log(e.target) // > li
   }
   //在ie678中使用e.srcElement中返回触发对象
   ```



2. e.type 返回事件类型

   ```javascript
   div.onclick = function (event) {
       console.log(event.type) // > click
   }
   ```

3. 阻止默认行为

   ```javascript
   // e.preventDeafult() 阻止默认行为（如链接跳转）
   var a = document.querySelector('a');
   a.addEventListener('click', fn);
   function fn(e) {
       e.preventDefault();
   }
   // ie678 使用e.returnValue阻止默认行为
   // 还可以利用return false 阻止默认行为，没有兼容性问题 特点：return后面代码不执行，而且只限于传统注册方式（如onclick）
   ```



4. 阻止冒泡

   ```javascript
   // e.stopPropagation() 
   // ie678中 使用 window.event.cancelBuble = true
   /* <div calss="father">
   		<div class="son"></div>
   	</div>
   */
   var father =document.querySelector('.father');
   var son = document.querySelector('.son');
   father.addEventListener('click', fnOfFather, false);
   son.addEventListener('click', fnOfSon, false);
   function fnOfFather() {
       alert('father');
   }
   function fnOfSon(e) {
       alert('son');
       e.stopPropagation();
   }
   // > 提示：'son'
   ```

5. 事件委托（代理、委派）

   ```javascript
   // 将事件监听器设置在父节点上，用冒泡原理影响设置每个子节点
   // 只访问了一次dom，提高了程序性能
   /* <ul>
   		<li></li>
   		<li></li>
   		<li></li>
   		<li></li>
   		<li></li>
   	</ul>
   */
   var ul = document.querySelector('ul');
   ul.addEventListener('click', fn);
   function fn(e) {
       e.target.style.backgroundColor = 'pink';
   }
   ```

   优势：==节省内存消耗==

6. 鼠标事件

   ```javascript
   // 1.contextmenu 禁用右键菜单
   document.addEventListener('contextmenu', fn);
   function fn(e) {
       e.preventDefault();
   }
   
   // 2.selectStart 禁止选中文字
   document.addEventListener('selectStart', fn);
   function fn(e) {
       e.preventDefault();
   }
   ```

7. 鼠标事件对象

   ```javascript
   // 1. e.clientX   e.clientY 鼠标相对于可视窗口的X、Y坐标
   // 2. e.pageX   e.pageY 鼠标相对于文档页面的X，Y坐标
   // 3. e.screenX   e.screenY  鼠标相对于屏幕的X，Y坐标
   // ie9以上兼容
   ```

8. 键盘事件

   1. onkeyup 某个按键被松开时触发
   2. onkeydown 某个按键被按下时触发  按着不松会一直触发
   3. onkeypress 某个按键被按下时触发 按着不松会一直触发（不识别功能键，比如ctrl shift 箭头等）

   ```javascript
   // keydown 会优先于keypress先执行
   document.addEventListener('keypress', function() {
       alert('press');
   })
   document.addEventListener('keydown',function() {
       alert('down');
   })
   // 警示框 down 警示框 press
   ```

9. e.keyCode 返回对应按键ascii码值

   ```javascript
   document.addEventListener('keydown', function (e) {
       console.log(e.keyCode);
       //keyup和keydown 不区分大小写字母 a 和 A 的keyCode都是65
   })
   document.addEventListener('keypress', function (e) {
       console.log(e.keyCode);
       //keypress 区分大小写字母 a：65 A：97
   })
   ```

   

10. e.key

    ```javascript
    // 文本框获得焦点
    var search = document.querySelector('input');
    var con = document.querySelector('.con')
    document.addEventListener('keyup', function (e) {
        if (e.key == 's' || e.key == 'S') {
            search.focus();
        }
    })
    ```



---

## 22. BOM

### 22.1 BOM概述

​	BOM(Browser Object Model)，浏览器对象模型，独立于内容与浏览器窗口进行交互的对象，核心是window

​	BOM是浏览器厂商在浏览器上定义的，兼容较差

​	BOM比DOM更大，包含DOM

![image-20230207232205045](C:\Users\PC\AppData\Roaming\Typora\typora-user-images\image-20230207232205045.png)

​	window对象是浏览器的顶级对象。

​		它是JS访问浏览器窗口的一个接口

​		它是一个全局对象，定义在全局中的==变量、函数==都会变成window对象的==属性和方法==

​		注意一个特殊属性<span style='color:red;'>window.name</span>



### 22.2 页面加载事件

1. window.onload  文档内容完全加载完毕（包括图像、脚本文件、CSS文件等）后才会触发改事件。

```javascript
window.onload = function() {}
// 或 
window.addEventListener('load', function() {})
```

​	注意：有了window.onload，就可以把JS代码写到页面元素上方

​		window.onload传统注册方式只能写一次，如果有多个，会以最后一个window.onload为准，建议使用后者window.addEventListener('load', function() {})



2. DOMContentLoaded 事件，仅当DOM加载完成，不包括样式表、图片、flash等

​	加快了多图片网页与用户的交互。

```javascript
document.addEventListener('DOMContentLoaded', function() {})
```



### 22.3 调整窗口大小事件

1. window.onresize = function() {}

2. window.addEventListener("resize", function(){});

   调整窗口大小事件，当窗口大小调整时就调用

   window.innerWidth 返回页面大小

   ```javascript
   var div = document.querySelector('div')
   window.addEventListener('resize', function() {
       if(window.innerWidth < 800px) { 
           div.style.display = 'none'; 
       } else {
           div.style.display = 'block';
       }
   })
   ```

   

### 22.4 定时器

1. setTimeOut(函数, 延迟毫秒数)，可以省略window直接调用

   ```javascript
   function callBack() {
       console.log('时间到');
   }
   setTimeOut(callBack, 2000);
   // 或setTimeOut('callBack()', 2000);
   ```

   页面中可能有很多定时器，可以加标识符

   ```javascript
   var timer1 = setTimeOut(callBack, 2000);
   var timer2 = setTimeOut(callBack, 5000);
   ```

   

2. 回调函数：某个事件触发才调用的函数

   如element.addEventListener('click', fn)

   setTimeOut(fn, 延迟时间)

   ```javascript
   // 五秒关闭广告
   var ad = document.querySelector('.ad');
   setTimeOut(function() {
       ad.style.display = 'none';
   }, 5000)
   ```

3. 停止setTimeOut()计时器

   window.clearTimeOut(timeout ID)

   ```javascript
   // 停止计时器
   var btn = document.querySelector('buton');
   var timer = setTimeOut(function() {
       console.log('时间到');
   }, 5000);
   btn.addEventListener('click', function() {
       clearTimeOut(timer);
   })
   ```

4. setInterval(回调函数, 间隔毫秒数)

   每间隔一段时间，调用一次回调函数

   用于做轮播图和倒计时

   ```javascript
   // 每隔1s输出当前秒数
   var time = 0;
   console.log(time);
   setInterval(function() {
       console.log(++time);
   },1000);
   ```

5. clearInterval(interval ID)

   清除定时器

   ```javascript
   var begin = document.querySelector('.begin');
   var stop = document.querySelector('.stop');
   var timer = null;
   begin.addEventListener('click', function() {
       timer = setInterval('hey~', 1000);
   })
   stop.addEventListener('click', function() {
       clearInterval(timer);
   })
   ```

   

### 22.6 this指向谁？

1. 全局作用域和普通函数中，this指向window（定时器中，this指向window）

   ```javascript
   console.log(this) // > window
   
   function fn() {
       console.log(this)// > window
   }
   //window.fn()
   
   setOutTime(function() {
       console.log(this)// > window
   }, 1000);
   // window.setOutTime()
   ```

2. 方法中的this指向调用者

   ```javascript
   var o = {
       sayHi: function() {
           console.log(this);
       }
   }
   o.sayHi() // > o
   
   
   btn.addEventListener('click', function() {
       console.log(this);// > btn
   })
   ```

3. 构造函数中this指向构造函数的实例

   ```javascript
   function Fun() {
       console.log(this)
   }
   var fun = new Fun();// > fun
   ```

   

### 22.7 单线程

1. 单线程：所有的任务都需要排队，导致页面渲染不连贯

​	任何DOM元素进行添加和删除，必须先添加后删除。

​	h5允许JS脚本创建多个线程。如setTimeOut会创建新的任务队列

​	同步：逻辑上先后执行的任务，执行完前一个再执行后一个

​	异步：逻辑上能同时进行的任务，允许同时执行

```javascript
console.log(1)
setTimeOut(function() {
    console.log(3);
}, 1000)
console.log(2);
// > 1
// > 2
// > 3
```

2. JS执行机制
   1. 先执行执行栈中的同步任务
   2. 异步任务（回调函数）放入任务队列中
   3. 执行栈中所有同步任务执行完毕，按顺序读取任务队列中的异步任务，将异步任务放入执行栈中，再依次执行

3. 异步进程处理

   存在异步任务时，将异步任务加入任务队列。

4. 事件循环

   执行栈为空时不断循环访问任务队列，若存在异步任务，则加入执行栈。

   ![image-20230208211621239](C:\Users\PC\AppData\Roaming\Typora\typora-user-images\image-20230208211621239.png)



### 22.8 location对象

​	location属性用于获取或设置窗体的URL，并可以用于解析URL。该属性返回的是一个对象，成为location对象

​	URL(Uniform Resource Locator, URL)统一资源定位符，互联网上每个文件都有唯一URL，指出文件的位置以及浏览器的处理方式

```
URL一般语法格式为
protocol://host[:port]/path/[?query]#fragment
如：http://www.itcast.cn/index.html?name=andy&age=18#link
```

| 组成     | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| protocol | 通信协议，如http，ftp，maito等                               |
| host     | 主机(域名)                                                   |
| port     | 端口号 可选，省略时使用方案的默认端口 如http使用默认端口80   |
| path     | 路径，有零或多个'/'符号隔开的字符串，一般用来表示主机上的一个目录或文件地址 |
| query    | 参数 以键值对的形式，通过&符号分隔开来                       |
| fragment | 片段 #后面内容 常见于链接 锚点                               |

1. location对象的属性

| location对象属性  | 返回值                          |
| ----------------- | ------------------------------- |
| location.href     | 获取或设置 整个URL              |
| location.host     | 返回主机(域名)                  |
| location.port     | 返回端口号 如果未写返回空字符串 |
| location.pathname | 返回路径                        |
| location.search   | 返回参数                        |
| location.hash     | 返回片段                        |

2. location.href 实现网页跳转

```javascript
var div = document.querySelector('div');
div.addEventListener('click', function() {
    location.href = 'https://www.baidu.com';
})
```

3. 利用location.search将数据传到另一个网站

```html
// login.html
<body>
    <form action="index.html">
        用户名：<input type="text" name="uname">
        <input type="submit" value="登录">
    </form>
</body>
```

```javascript
// index.html
var div = document.querySelector('div');
var para = location.search.substring(1);
var arrOfName = para.split('=');
var uname = arrOfName[1];
div.innerHTML = '<span style="color:red;">' + uname + '</span>欢迎你';
```



4. location.assign() 实现网页跳转

   记录浏览历史

   ```javascript
   var btn = document.querySelector('button');
   btn.addEventListener('click', function() {
       // 记录浏览历史，所以可以实现后退功能
       location.assign('https://www.itcast.cn');
   })
   ```

5. location.replace() 实现网页跳转

   不记录浏览历史

   ```javascript
   var btn = document.querySelector('button');
   btn.addEventListener('click', function() {
       // 不记录浏览历史，不能后退
       location.replace('https://www.itcast.cn');
   })
   ```

6. location.reload() 刷新页面

   ```javascript
   location.reload()； // 刷新，相当于F5
   location.reload(true); // 强制刷新，相当于ctrl+F5，会清除缓存，重新从服务器中下载数据
   ```



### 22.9 navigator对象

​	包含关于浏览器的信息，经常使用的是userAgent，可以返回由客户机发送服务器user-agent头部的值

```javascript
if(navigator.userAgent.match(/(phone|pad|iPhone...)/i)) {
    window.loaction.href = ""; // 手机端页面
} else {
    window.location.href = ""; // 移动端页面
}
```

### 22.10 history对象

| history对象方法 | 作用                                                   |
| --------------- | ------------------------------------------------------ |
| back()          | 后退功能                                               |
| forward()       | 前进功能                                               |
| go(参数)        | 前进后退功能 参数为1前进一个页面，参数为-1后退一个页面 |

一般在OA系统中见到



### 22.11 pageshow事件

​	pageshow在页面显示时触发，无论页面是否来自缓存、重新加载页面。pageshow会在load事件触发后触发；

​	根据事件对象中的persisted判断是否是缓存中的页面触发的pageshow事件；该事件要给window添加

```javascript
window.addEventListener('pageshow', function() {
    if(e.persisted) { // 如果页面是从缓存取回来的页面
        setRemUnit();
    }
})
```



---

## 23.网页特效

### 23.1 offset属性

​	1.可以动态返回网页元素位置（偏移）、大小等

| offset系列属性       | 作用                                                |
| -------------------- | --------------------------------------------------- |
| element.offsetParent | 返回该元素带有定位的父级元素                        |
| element.offsetTop    | 返回元素相对带有定位父元素上方的偏移                |
| element.offsetLeft   | 返回元素相对带有定位父元素左边的偏移                |
| element.offsetWidth  | 返回自身包括padding、边框、内容区域的宽度，不带单位 |
| element.offsetHeight | 返回自身包括padding、边框、内容区域的高度，不带单位 |

2. offset和style的区别

   | offset                               | style                                    |
   | ------------------------------------ | ---------------------------------------- |
   | offset可以得到“任意”样式表中的样式值 | 只能得到 行内 样式表的样式值             |
   | offset系列获得的数值 没有单位        | style.width获得的数值 带有单位的字符串   |
   | offsetWidth包含padding+border+width  | style.width获得不包含padding和border的值 |
   | offsetWidth是 只读属性               | style.width 可读可写                     |
   | 想要获取元素大小位置，使用offset     | 想要给元素更改值，使用style              |

   

### 23.2 模态框

1. 遮挡层mask和模态框，当点击buttonOn时，将display设置为block

2. 模态框添加拖动效果

   ```javascript
   var div = document.querySelector('div');
   div.addEventListener('mousedown', function (e) {
       var constX = e.pageX - this.offsetLeft;
       var constY = e.pageY - this.offsetTop;
       document.addEventListener('mousemove', moveBox);
       function moveBox(e) {
           div.style.left = (e.pageX - constX) + 'px';
           div.style.top = e.pageY - constY + 'px';
       }
       document.addEventListener('mouseup', function () {
           document.removeEventListener('mousemove', moveBox);
       })
   })
   ```

3. 放大镜

   ```javascript
   var com = document.querySelector('.commodity');
   var img = document.querySelector('img');
   var mag = document.querySelector('.magnifier');
   var dsp = document.querySelector('.display');
   com.addEventListener('mouseover', function () {
       mag.style.display = 'block';
       dsp.style.display = 'block';
       dsp.style.background = 'url(' + img.src + ') no-repeat';
       // 自动调整放大图片的尺寸 com.offsetWidth / mag.offsetWidth 是缩略图和放大镜的比值，dsp.offsetWidth是放大窗口的尺寸
       dsp.style.backgroundSize = com.offsetWidth / mag.offsetWidth * dsp.offsetWidth + 'px';
       // 放大镜设置
       com.addEventListener('mousemove', function (e) {
           if (e.pageX - com.offsetLeft - mag.offsetWidth / 2 <= 0) {
               mag.style.left = 0;
           } else if (e.pageX - com.offsetLeft + mag.offsetWidth / 2 >= com.offsetWidth) {
               mag.style.left = com.offsetWidth - mag.offsetWidth + 'px';
           } else {
               mag.style.left = e.pageX - com.offsetLeft - mag.offsetWidth / 2 + 'px';
           }
           if (e.pageY - com.offsetTop - mag.offsetHeight / 2 <= 0) {
               mag.style.top = 0;
           } else if (e.pageY - com.offsetTop + mag.offsetHeight / 2 >= com.offsetHeight) {
               mag.style.top = com.offsetHeight - mag.offsetWidth + 'px';
           } else {
               mag.style.top = e.pageY - com.offsetTop - mag.offsetWidth / 2 + 'px';
           }
           dsp.style.backgroundPosition = -dsp.offsetWidth / mag.offsetWidth * parseFloat(mag.style.left) + 'px ' + (-dsp.offsetWidth / mag.offsetWidth) * parseFloat(mag.style.top) + 'px';
       })
       com.addEventListener('mouseout', function () {
           mag.style.display = 'none';
           dsp.style.display = 'none';
       })
   })        
   ```

   

### 23.3 元素可视区client系列

| client系列属性       | 作用                                                         |
| -------------------- | ------------------------------------------------------------ |
| element.clientTop    | 返回元素上边框的大小                                         |
| element.clientLeft   | 返回元素左边框的大小                                         |
| element.clientWidth  | 返回自身包括padding、内容区的宽度、不含边框，返回数值不带单位 |
| element.clientHeight | 返回自身包括padding、内容区的高度，不含边框，返回数值不带单位 |



### 23.4 立即执行函数（自执行函数）

​	不需要调用，能够自己执行的函数

```javascript
// 不需要调用，能够自己执行的函数
(function fn(形参) {})(实参) 或 (function(形参) {} (实参))

// 示例：
(function() {
    console.log(2);
})();
// > 2

// 示例：传参
(function(a, b) {
    console.log(a + b);
})(1, 2);
// > 3
```

​	立即执行函数最大的作用就是创建了一个<span style='color:red'>独立作用域</span>，不会有命名冲突

​	淘宝flexible.js



### 23.5 元素滚动scroll系列

| scroll系列属性       | 作用                                         |
| -------------------- | -------------------------------------------- |
| element.scrollTop    | 返回被卷去的上测距离，返回数值不带单位       |
| element.scrollLeft   | 返回被卷去的左侧距离，返回数值不带单位       |
| elemeng.scrollWidth  | 返回自身实际宽度，不含边框，返回数值不带单位 |
| element.scrollHeight | 返回自身实际高度，不含边框，返回数值不带单位 |



scrollHeight : 与clientHeight不同，scrollHeight返回的是真正内容的高度大小

scrollWidth同理



scroll事件：滚动条滚动时会发生的事件

```javascript
var div = document.querySelector('div');
div.addEventListener('scroll', function () {
    console.log(div.scrollTop);
});
```

另外，整个页面被卷去的上侧和左侧，用 window.pageYOffset(或window.scrollY) 和 window.pageXOffset(或window.scrollX) 获得

例如：侧边栏固定、header固定、返回顶部

```javascript
// 侧边栏固定
var sliderBar = document.querySelector('.slider-bar');
var banner = document.querySelector('.banner')
var bannerTop = banner.offsetTop;
document.addEventListener('scroll', function() {
    if(window.pageYOffset >= bannerTop) {
        sliderBar.style.position = 'fixed';
        sliderBar.style.top = sliderBar.offsetTop - bannerTop + 'px'
    } else {
        sliderBar.style.position = 'absolute';
        sliderBar.style.top = '300px';
    }
})
```

| 三大系列大小对比    | 作用                                                         |
| ------------------- | ------------------------------------------------------------ |
| element.offsetWidth | 返回自身包括padding、边框、内容区的宽度，返回数值不带单位    |
| element.clientWidth | 返回自身包括padding、内容区的宽度，不含边框，返回数值不含单位 |
| element.scrollWidth | 返回自身实际宽度，不含边框，返回数值不带单位                 |

三个系列对比

| 作用         | 使用方法                                 |
| ------------ | ---------------------------------------- |
| 获取元素大小 | clientWidth  clientHeight                |
| 获取滚动距离 | scrollTop    scrollLeft                  |
| 页面滚动距离 | window.pageYOffset    window.pageXOffset |



### 23.6 mouseenter和mouseover事件

​	mouseenter: 经过自身盒子会触发

​	mouseover: 经过自身盒子会触发，经过子盒子还会触发(冒泡)

​	

​	类似的还有mouseout和mouseleave

​	mouseout：经过自身盒子会触发，经过子盒子还会触发(冒泡)

​	mouseleave：经过自身盒子会触发



### 23.7 JS动画原理

1. 匀速平移

```javascript
var div = document.querySelector('div');
var timer = setInterval(function () {
    if (div.offsetLeft >= 400) {
        clearInterval(timer);
    }
    div.style.left = div.offsetLeft + 1 + 'px';
}, 10)
```

2. 封装函数：平移(对象，移动的距离)

```javascript
function animate(obj, target) {
    var timer = setInterval(function () {
        if (obj.offsetLeft >= target) {
            clearInterval(timer);
        }
        obj.style.left = obj.offsetLeft + 1 + 'px';
    }, 10);
}
```

3. 缓动动画：每次移动就让速度降低

```javascript
function animate(obj, target) {
    var step = (target - obj.offsetLeft) / 10;
    step = step > 0 ? Math.ceil(step) : Math.floor(step); 
    var timer = setInterval(function () {
        if (obj.offsetLeft == target) {
            clearInterval(timer);
        }
        obj.style.left = obj.offsetLeft + step + 'px';
    }, 10);
}
```

4. 缓动动画添加回调函数：将函数作为实参传入函数

```javascript
function animate(obj, target, callback) {
    var timer = setInterval(function () {
        if (obj.offsetLeft >= target) {
            clearInterval(timer);
            // 将callback写在clear下面，表示clear执行完毕后再执行回调函数
            if (callback) {
                callback();
            }    
        }
        obj.style.left = obj.offsetLeft + 1 + 'px';
    }, 20);
}
```

5. 轮播图
    实现功能：1. 鼠标经过轮播图模块，左右按钮显示，离开隐藏左右按钮；鼠标经过轮播图模块，停止轮播，离开时重新轮播
    2. 点击左右按钮能自动切换图片
    3. 图片播放同时，小圆圈模块随即一起变化
    4. 点击小圆圈可播放相应图片

6. 无缝滚动
    复制第一个li，插在最后一个li之后，当轮播图继续向右滚动时，迅速跳回第一张，再完成滚动动画

7. 手动调用点击事件
    arrow.click（）

8. 定时器的开启和关闭
    clearInterval（timer）
    timer = null

    timer = 。。。

9. 节流 
    设置节流阀var flag = true
    每次点击️时 if（flag）{ flag = false 。。。。。。}
    短路运算 callback && callback（）

  ​        callback = function() { flag = true; }

10. 筋斗云 鉴定为猪都能做

### 23.8 移动端动画

1. 最常使用的触摸列表

  | 事件名     | 对应事件 |
  | ---------- | -------- |
  | touchstart | 触摸     |
  | touchmove  | 移动     |
  | touchend   | 松开触摸 |

  

  | 属性名         | 对应属性                                       |
  | -------------- | ---------------------------------------------- |
  | touches        | 触摸屏幕的手指集合                             |
  | targetTouches  | 触摸目标元素的手指集合                         |
  | changedTouches | 手指状态发生变化的手指集合，从无到有，从有到无 |

  一般使用element.targetTouches[0]来获取手指

  

2. 移动端拖拽元素

  ```javascript
  var startX = 0; //手指起始位置
  var startY = 0;
  var x = 0;//元素起始位置
  var y = 0;
  
  var move = div.addEventListener(“touchstart”, function (e) {
      startX = e.targetTouches[0].pageX;
      startY = e.targetTouches[0].pageY;
      x = this.offsetLeft;
      y = this.offsetTop; 
      div.addEventListener(“touchmove”, function (e) {
          this.style.left = x + e.targetTouch[0].pageX - startX + “px”;
          this.style.top = y + e.targetTouch[0].pageY - startY + “px”;
          e.preventDefault(); // 阻止默认事件
      })
      div.addEventListener(‘touchend’, function(e) {
          removeEventListener(move);
      })
  })
  ```

  

  

3. 移动端无缝动画
    在轮播图ul.children[0]前面插入最后一个li的克隆体ul.children[ul.length-1]，并且ul.appendChildren(ul.children[1]);

    使用跳转 transition = 'none';来进行左右无缝动画

    

4. 用translate和transition代替left和transition

    

5. transitionend 过渡结束事件
    element.addEventListener(‘transitionend’, function () {})

    用于进行过渡后的跳转，实现无缝动画

    

6. classList 返回类名列表

    ```html
    <div class = "one two three"></div>
    <script>
        console.log(div.classList[0]) // > one
        classList.add(‘类名’) 添加一个类名
        classList.remove(‘类名’) 删除一个类名
        classList.toggle(‘类名’) 切换一个类名（有就删除，没有就加上）
    
        // 切换小圆点
        ol.querySelector(‘.current’).classList.remove(‘current’);
        ol.children[index].classList.add(‘current’);
    </script>
    ```

    

    

    

7. 移动端轮播图滑动效果
    ```javascript
    var ul = document.querySelector('ul');
    var ol = document.querySelector('ol');
    // 这里用translate代替position: absolute;left
    var translatex = 0;
    var startX = 0;
    // moveX是滑动距离，往左拖动为负，往右拖动为正
    var moveX = 0;
    // 设置初始序号为1
    var index = 1;
    // 设置小圆点
    for (var i = 0; i < ul.children.length; i++) {
        li = document.createElement('li');
        ol.appendChild(li);
        if (!i) {
            li.className = 'current';
        }
    }
    // 复制第一个li插在ul最后面
    var firstLiCloned = ul.children[0].cloneNode();
    ul.appendChild(firstLiCloned);
    // 复制最后一个li插在ul最前面
    var lastLiCloned = ul.children[ul.children.length - 2].cloneNode();
    ul.insertBefore(lastLiCloned, ul.children[0]);
    // li的宽度存一下
    var w = ul.children[0].offsetWidth;
    // 设置ul初始位置
    ul.style.transform = 'translateX(' + -index * w + 'px)';
    // 加入事件
    // 自动轮播
    var timer = setInterval(function () {
        index++;
        translatex = -index * w;
        ul.style.transition = 'transform .3s';
        ul.style.transform = 'translateX(' + translatex + 'px)';
        document.querySelector('.current').className = '';
        ol.children[(index - 1) % ol.children.length].className = 'current';
    }, 2000)
    // 手指事件
    ul.addEventListener('touchstart', function (e) {
        e.preventDefault();
        clearInterval(timer);
        startX = e.targetTouches[0].pageX;
    })
    ul.addEventListener('touchmove', function (e) {
        e.preventDefault();
        moveX = e.targetTouches[0].pageX - startX;
        translatex = -index * w + moveX;
        ul.style.transition = 'none';
        ul.style.transform = 'translateX(' + translatex + 'px)';
    
    })
    ul.addEventListener('touchend', function () {
        if (Math.abs(moveX) > 50) {
            if (moveX > 0) {
                index--;
                translatex = -index * w;
                ul.style.transition = 'transform .3s';
                ul.style.transform = 'translateX(' + translatex + 'px)';
                document.querySelector('.current').className = '';
                ol.children[(index - 1) % ol.children.length].className = 'current';
            } else {
                index++;
                translatex = -index * w;
                ul.style.transition = 'transform .3s';
                ul.style.transform = 'translateX(' + translatex + 'px)';
                document.querySelector('.current').className = '';
                ol.children[(index - 1) % ol.children.length].className = 'current';
            }
        } else {
            translatex = -index * w;
            ul.style.transition = 'transform .1s';
            ul.style.transform = 'translateX(' + translatex + 'px)';
        }
        timer = setInterval(function () {
            index++;
            translatex = -index * w;
            ul.style.transition = 'transform .3s';
            ul.style.transform = 'translateX(' + translatex + 'px)';
            document.querySelector('.current').className = '';
            ol.children[(index - 1) % ol.children.length].className = 'current';
        }, 2000)
    })
    
    ul.addEventListener('transitionend', function () {
        if (index <= 0) {
            index = ul.children.length - 2;
            translatex = -index * w;
            ul.style.transition = 'none';
            ul.style.transform = 'translateX(' + translatex + 'px)';
        } else if (index >= ul.children.length - 1) {
            index = 1;
            translatex = -index * w;
            ul.style.transition = 'none';
            ul.style.transform = 'translateX(' + translatex + 'px)';
        }
    })
    ```

    

8. 返回顶部

  ```javascript
  window.scroll(x, y); // 页面滚动到x，y处
  
  var goBack = document.querySelector(‘.goBack’);
  var hav = document.querySelector(‘nav’);
  window.addEventListener(‘scroll’, function() {
      if(window.pageYoffset >= nav.offsetTop) {
          goBack.style.display = ‘block’;
      } else {
          goBack.style.display = ‘none’;
      }
  })
  
  goBack.addEventListener(‘click’, function() {
      window.scroll(0, 0);
  })
  ```

  

  

8. 解决移动端300ms延迟问题
    1. 使用user-scalable = 0
    2. 封装函数function tap() {obj, callback}
    3. 利用fastclick插件  // JS插件是js文件，功能单一，体积小，能满足特定需求，如animate.js

9. swiper 轮播图
www.swiped.com.cn
www.superslide2.com
github.com/cubiq/iscroll

10. 移动端视频插件

11. 移动端常用开发框架
    框架：一套较为完整的解决方案，框架的控制权在框架本身，使用者要按照框架所规定的某种规范进行开发
    如bootstrap Vue Angular React 既能开发PC端，也能开发移动端
    常用移动端框架有swiper superslide iscroll

### 23.9 会话存储和本地存储
1. 特性：数据存储在用户浏览器中，设置、读取方便，刷新不丢失
    容量较大，sessionStorage约5m，localStorage约20m
    只能存储字符串，可将JSON.stringify()编码后存储

2. sessionStorage（会话存储） 生命周期为关闭浏览器窗口
    同一个窗口下数据可共享
    以键值对形式存储使用
    
    ```javascript
    // 存储数据：sessionStorage.setItem(key,value)
    // 获取数据：sessionStorage.getItem(key)
    // 删除数据：sessionStorage.removeItem(key)
    // 清除所有数据: sessionStorage.clear()

3.localStrage（本地存储） 生命周期为永久
    关闭页面也保存数据
    ==可以多页面共享==
存储：localStorage.setItem(key, value);
获取：localStorage.getItem(key);
删除：localStorage.removeItem(key);
清空：localStorage.clear();

4. 记住用户名
    ```html
    <input type="text" id="username">
    <input type="checkbox" id="remember"> 记住用户名
    <script>
        var username = document.querySelector('#username');
        var remember = document.querySelector('#remember');
        if (localStorage.getItem('username')) {
            username.value = localStorage.getItem('username')
            remember.checked = true;
        }
        remember.addEventListener('change', function () {
            if (this.checked) {
                localStorage.setItem('username', username.value);
            } else {
                localStorage.removeItem('username');
            }
        })
    ```
    
    

## 24.jQuery
### 24.1 jQuery特点
1. JS库：将一些功能封装成函数，存在js代码中
2. jQuery优点
    简化操作
    轻量级
    链式编程，隐式迭代
    支持插件扩展
    免费开源

### 24.2 jQuery的使用
1. 引入jQuery.js
2. 编写js代码

### 24.3 jQuery的一般语法
1. 入口函数
  ```html
  <div></div>
  <script>
      $(function () { // 等同于DOMContentLoaded
          $('div').hide();// 隐藏元素
      })
  	// 或写成$(document).ready(function() {})
  </script>
  ```

  

2. jQuery的顶级对象\$
    在jQuery中，\$是jQuery**别名**，相当于原生js中的window
    用\$包装元素成为jQuery对象，就可以调用jQuery方法

    ```javascript
     $('div').hide();
    ```

    

3. DOM对象和jQuery对象
    DOM对象：用原生js获取的对象

    ```javascript
    var div = document.querySelector(‘div’);
    div.style.display = 'none';
    ```


    jQuery对象：用jQuery方法获取的对象
    
    ```javascript
    console.log($(‘div’); )// 获取的是一个伪数组
    $('div').hide();
    ```


​    

    jQuery对象只能使用jQuery方法，DOM对象只能使用原生js方法，不能混用
    
    jQuery对象和DOM对象可以互相转换


    ```javascript
    // DOM转jQuery
    $(DOM对象)
    // jQuery转DOM
    $(‘div’)[index]  or  \$(‘div).get(index)
    ```

​	

### 24.4 jQuery常用API

1. 选择器

    ```javascript
    // $(‘选择器’)  包括层级选择器,如
    $('ul li>a')
    ```

    

2. 设置css样式（隐式迭代）

    ```javascript
    $(‘选择器’).css(‘属性名’, ‘属性值’) // 相当于做了一次for循环，给每一个元素设置css属性
    ```

    

3. 筛选选择器

  | 语法       | 用法           | 描述                         |
  | ---------- | -------------- | ---------------------------- |
  | :first     | \$(‘li:first’) | 获取第一个li元素             |
  | :last      | \$(‘li:last’)  | 获取最后一个li元素           |
  | :eq(index) | $('li:eq(2)')  | 获取li元素中，索引号为2的    |
  | :odd       | $('li:odd')    | 获取li元素中，索引号为奇数的 |
  | :even      | $('li:even')   | 获取li元素中，索引号为偶数的 |

​    

4. jQuery筛选方法(重点)

   | 语法               | 用法                           | 说明                                               |
   | ------------------ | ------------------------------ | -------------------------------------------------- |
   | parent()           | $("li").parent();              | 查找父级                                           |
   | children()         | $("ul").children("li")         | 相当于$("ul>li")，最亲一级                         |
   | find(selector)     | $("ul").find("li")             | 相当于$("ul li")，后代选择器                       |
   | siblings(selector) | $(".first").siblings("li")     | 查找兄弟节点，不包括本身                           |
   | nextAll([expr])    | $(".last").nextAll()           | 查找当前元素之后的所有同辈元素                     |
   | prevAll([expr])    | $(".first").prevAll()          | 查找当前元素之前的所有同辈元素                     |
   | hasClass(class)    | $("div").hasClass("protected") | 检查当前元素是否含有某个特定类，如果有，则返回True |
   | eq('index')        | $('li').eq(2);                 | 相当于$('li:eq(2)'),index从0开始                   |

   

### 24.5 下拉菜单

```html
<ul class="nav">
    <li>
        <a href="javascript:;">menu1</a>
        <ul>
            <li>1.1</li>
            <li>1.2</li>
            <li>1.3</li>
        </ul>
    </li>
    <li>
        <a href="javascript:;">menu2</a>
        <ul>
            <li>2.1</li>
            <li>2.2</li>
            <li>2.3</li>
        </ul>
    </li>
    <li>
        <a href="javascript:;">menu3</a>
        <ul>
            <li>3.1</li>
            <li>3.2</li>
            <li>3.3</li>
        </ul>
    </li>
    <li>
        <a href="javascript:;">menu4</a>
        <ul>
            <li>4.1</li>
            <li>4.2</li>
            <li>4.3</li>
        </ul>
    </li>
</ul>
<script>
    $(function () {
        $('.nav>li').mouseover(function () {
            $(this).children('ul').show();
        });
        $('.nav>li').mouseleave(function () {
            $(this).children('ul').hide();
        })
    })
</script>
```

### 24.6 排他思想

```html
<ul class="nav">
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
</ul>
<script>
    $(function () {
        $('li').click(function () {
            $(this).css('background-color', 'skyblue')
            $(this).siblings('li').css('background-color', '')
        })
    })
</script>
```



### 24.7 链式编程

```javascript
// 通常的写法
$(function () {
    $('li').click(function () {
        $(this).css('background-color', 'skyblue')
        $(this).siblings('li').css('background-color', '')
    })
})

// 链式编程
$(function () {
    $('li').click(function () {
        $(this).css('background-color', 'skyblue').siblings('li').css('background-color', '')
    })
})
```



### 24.8 样式操作

1. 修改css样式

   参数只写属性名，则返回属性值

   ```javascript
   $('div').css('color') >> 'red'
   ```

   css('属性名1'：'属性值1', '属性名2':'属性值2'...) 改变多组属性

   以对象的形式修改，可以不加引号

   ```javascript
   $('div').css({
       width:400, // 注意这里用逗号
       height:400,
       backgroundColor: 'red' // 复合属性采取驼峰命名法，red是非数，加引号
   })
   ```

   

2. 设置类样式方法（改变类名）

   addClass('类名') 添加类名

   ```javascript
   $('div').addClass('current')
   ```

   removeClass('类名') 删除类名

   ```javascript
   $('div').removeClass('current')
   ```

   toggleClass('类名') 切换类名(有->无，无->有)

   ```javascript
   x $('div').toggleClass('current')
   ```

   

 ### 24.9 jQuery效果

| 效果       | 代码                                        |
| ---------- | ------------------------------------------- |
| 显示/隐藏  | show()、hide()、toggle()                    |
| 滑动       | slideDown()、slideUp()、slideToggle()       |
| 淡入淡出   | fadeIn()、fadeOut()、fadeToggle()、fadeTo() |
| 自定义动画 | animate()                                   |

1. 显示隐藏效果

   ```javascript
   show([speed,[easing],[fn]]) // 以左上角为缩放原点
   // speed:可用参数slow、normal、fast，或表示动画时长的毫秒数
   // easing: 指定切换效果，默认swing，可用linear
   // fn: 回调函数
   ```

   

2. 滑动

   ```javascript
   slideDown([speed,[easing],[fn]]) // 以元素最上方的x轴为缩放原轴
   ```

   

3. 事件切换（hover）

   ```javascript
   hover(function() {}, function() {}) // 第一个是经过时的函数，第二个是离开时的函数，对用mouseenter和mouseleave
   // 如果只写一个函数，那么鼠标经过和离开都会触发这个函数
   $('.nav>li').hover(function() {
       $(this).children('ul').slideDown()
   }, function() {
       $(this).children('ul').slideUp()
   })
   
   // 等价于
   $('.nav>li').hover(function() {
       $(this).children('ul').slideToggle()
   })
   ```

   

4. 停止动画(节流、阻止动画排队)

   ```javascript
   // 要写在动画的前面
   $('.nav>li').hover(function() {
       $(this).children('ul').stop().slideToggle()
   })
   ```



5. 淡入淡出

   ```javascript
   $('div').hover(function() {
       $(this).silbings().stop().fadeTo(200,0.3)
   }, function() {
       $(this).silbings().stop().fadeTo(200,1)
   })
   ```

   

6. 自定义动画

   ```javascript
   animate(params,[speed],[easing],[fn])
   // params: 想要更改的样式属性，通过对象形式传递
   $('div').animate({
       left: 100,
       top: 100,
       opacity: 200,
       width: 200,
   }, 500)

### 24.10 jQuery属性操作

1. 获得固有属性 prop('属性名')

```javascript
可以获得元素本身自带的属性，如<a>中的href，input中的type、title等
$('a').prop('href') // > https://www.baidu.com

```

2. 设置固有属性 prop('属性名', '属性值')

   ```javascript
   $('a').prop('href', 'https://www.bilibili.com')
   ```

   可以获得checkbox是否被选中

   ```javascript
   $('input').change(function() {
       console.log($(this).prop('checked'))
   })
   ```

   

3. 自定义属性 

   获得：attr('属性名')、

   修改：attr('属性名', '属性值')

   类似于原生js中的getAttribute()和setAttriubte()

   可以获得data-开头的属性

   prop不能获得自定义属性

   ```javascript
   console.log($('div').attr('index'))
   ```

   

4. 数据缓存

   data('属性名', '属性值')

   将内容缓存在元素的内存里，==在DOM里不可见==

   能获取data-开头的属性，比如要获取data-index，就使用data('index')，如果属性值是数，那么返回数字型

   ```javascript
   $('div').data('uname') // 返回的是data-uname的值
   
   $("div").data("index", '1')
   $("div").data("index") // > 数值型1

5. 复选框

   使用:checked返回被选中checkbox

   ```javascript
   $('.checkAll').change(function () {
       $('.j-checkbox').prop('checked', $(this).prop('checked'))
   })
   $('.j-checkbox').change(function () {
       if ($(this).prop('checked')) {
           if($('.j-checkbox').length === $('.j-checkbox:checked').length) {
               $('.checkAll').prop('checked', true)
           }
       } else {
           $('.checkAll').prop('checked', false)
       }
   })
   ```

   

   

6. 获取、修改元素内容

   使用html()，相当于原生js的innerHTML

   使用text(), 相当于原生js的innerText

   ```javascript
   // 获取
   $('div').html()
   $('div').text()
   
   // 修改
   $('div').html('<span>123</span>')
   $('div').text('123')



7. 获得、修改表单的值

   使用val()，相当于原生js的value

   ```javascript
   // 获取
   $('input').val()
   // 修改
   $('input').val("123")
   ```

   

   

8. 返回祖先列表

   parents()，越亲的祖辈index越小，从0开始

   ```html
   <div class="one">
       <div class="two">
           <div class="three">
               <div class="four">我最小</div>
           </div>
       </div>
   </div>
   <script>
       $('.four').parents('one')
       // 等价于 $(".four").parents().eq(2)
   </script>
   ```

   

   

9. 保留两位小数

   toFixed(2)

   截取字符串substr()

   ```html
   <input type="text" name="" id="" value='1'>
   <button class="increase">+</button>
   <button class="decrease">-</button>
   <span class="unit">19.60</span>
   <span class="total">19.60</span>
   <script>
       $('.increase').click(function () {
           var n = $('input').val();
           n++;
           $('input').val(n)
           var total = ($('.unit').text() * n).toFixed(2)
           $('.total').text(total)
       })
       $('.decrease').click(function () {
           var n = $('input').val();
           if (n == 1) {
               return false;
           }
           n--;
           $('input').val(n)
           var total = ($('.unit').text() * n).toFixed(2)
           $('.total').text(total)
       })
   </script>
   ```



### 24.11 jQuery元素操作

1. 遍历

   jQuery封装了一个遍历函数

   ```html
   each(function(index, domEle) {}) // 回调函数第一个参数是索引号，第二个是dom对象
   
   <div>1</div>
   <div>2</div>
   <div>3</div>
   <script>
       var color = ['red', 'green', 'blue']
       var sum = 0;
       $("div").each(function(index, domEle) {
           $(domEle).css('color',color[index]) // dom对象没有css方法
           sum += parseInt($(domEle).text())
       })
       console.log(sum) // > 6
   </script>
   ```

   $.each() 可以遍历任意类型数组、对象，类比于for in

   ```javascript
   // 数组
   arr = ['red', 'green', 'blue']
   
   $.each(arr, function(i, ele) {
       console.log(i); // > 0 1 2
       console.log(ele);// > red green blue
   })
   // 对象
   $.each({name:'andy', age:18}, function(i, ele) {
       console.log(i); // name age
       console.log(ele);// andy 18
   })
   ```

   

### 24.12 动态创建标签

1. 创建:

   ```javascript
   var li = $("<li></li>")
   ```

   

2. 内部添加（子级）：

   ```javascript
   $("ul").append(li) // 添加在内容的最后面
   $("ul").prepend(li) // 添加在内容的最前面
   ```

   

3. 外部添加（同级）：

   ```javascript
   var div1 = $("<div></div>")
   var div2 = $('<div></div>')
   $('.test').after(div1) // 添加在元素的后面
   $('.test').before(div2) // 添加在元素前面
   ```

   

4. 删除

   ```javascript
   // element.remove() 清除节点本身
   $('div').remove()
   
   // element.empty('selector') 清空所有子元素
   $('ul').empty()
   
   // element.html("") 清空元素中的内容
   ```

   

### 24.13 jQuery尺寸

| 语法                               | 表示的尺寸                  |
| ---------------------------------- | --------------------------- |
| width()/height()                   | 不包括padding和border       |
| innerWidth()/innerHeight()         | 包括padding                 |
| outerWidth()/outerHeight()         | 包括padding和border         |
| outerWidth(true)/outerHeight(true) | 包括padding、border、margin |

### 24.14 jQuery位置

| 语法       | 表示的位置                                                   |
| ---------- | ------------------------------------------------------------ |
| offset()   | 相对于文档的偏移(top、left)，返回的是一个对象，包含top和left，可以修改偏移，如offset({top:10,left:30}) |
| position() | 相对于第一个有定位的父级元素的偏移，如果没有则以文档为坐标，只能获取，不能修改偏移 |

### 24.15 jQuery被卷去头部

| 语法        | 效果                   |
| ----------- | ---------------------- |
| scrollTop() | 返回或修改顶部卷去的值 |
| scrolLeft() | 返回或修改左侧卷去的值 |

一般使用

```javascript
$("body, html").animate({scrollTop:0})
```

来返回顶部，注意作动画的必须是元素，而不能是document

```javascript
页面正在滚动的回调函数
$(window).scroll(function() {
    if($(document).scrollTop() >= $(".recomment").offsetTop()) {
       $(".fixedool").fadeIn()
       } else {
       $(".fixedool").fadeOut()          
       }
})
```



### 24.16 jQuery事件注册

1. 基本注册方式：链式编程

   ```javascript
   $("div").click(function () {
       $(this).css('background-color', 'purple')
   }).mouseenter(function () {
       $(this).css('background-color', 'skyblue')
   })
   ```

   

2. 事件处理 on({}) 以对象的方式传递事件，可以绑定多个事件处理程序

   ```javascript
   $("div").on({
       mouseenter: function() {
           $(this).css("background-color", "skyblue")
       },
       click: function() {
           $(this).css("background-color", "purple")
       }
   })
   ```

   on还可以让多个事件触发同一个函数

   ```javascript
   $("div").on("mouseleave click", function() {
       $(this).css("background-color", "skyblue")
   }) 
   ```

   on还可以进行事件委派，将由子元素触发的事件绑定到父元素上

   ```javascript
   $(".d1").on("click", ".d2", function () { // 这里.d2只是一个特例，可以是子元素的子元素，但this指向的是子元素
       $(this).css("background-color", "purple")
   })
   ```

   on还可以给未来动态创建的元素绑定事件，而click不行

   ```javascript
   // 先动态创建一个li
   var li = $("<li>我是后来创建的</li>");
   $("ul").append(li);
   // $(li).click(function() {alert(11)}) 不起作用
   $("ul").on("click", "li", function() {
       alert(11);
   })
   ```

   

   3. 事件解绑

   ```javascript
   $("div").off() // 解绑所有事件
   $("div").off("click") // 解除点击事件
   $("ul").off("click", "li") // 解除事件委托
   ```

   

   4. 一次性事件：一个事件只能触发一次

   ```javascript
   $("div").one("click", function() {
       $(this).css("background-color", "red")
   })
   
   
   $("div").one({
       click: function () {
           $(this).css("background-color", "red")
       },
       mouseenter: function () {
           $(this).css("background-color", "skyblue")
       }
   })
   ```



5. 自动触发事件

   ```javascript
   1. 用on绑定事件，并用.type()触发
   $("div").on("click", function() {
       alert(1)
   })
   $("div").click()
   
   2. 使用trigger("type")
   $("div").trigger("click")
   
   3.使用triggerHandler("type")，不会触发默认事件
   $("div").triggerHandler("click")
   ```

   

4. 事件对象

   ```javascript
   1. 阻止默认事件
   $("div").on("click", function(event) {
       event.preventDefault() // 或使用return false
   })
   
   2. 阻止冒泡
   $("div").on("click", function(event) {
       event.stopPropagation()
   })
   ```

   

### 24.17 jQuery拷贝对象

1. 深拷贝和浅拷贝

   ```javascript
   $.extend([deep], target, obj, )
   第一个参数为是否深拷贝，默认为false浅拷贝
   第二个参数为保存拷贝对象的目标
   第三个参数为被拷贝的对象
   
   浅拷贝：将被拷贝对象中的 复杂数据类型 仅仅传一个地址回来，因此改变其中的复杂数据类型，会使原对象和拷贝对象都发生改变
   var targetObj = {
       id: 0
   }
   var obj = {
       id: 1,
       msg: {
       	age: 18,
       	name: 'andy'
   	}
   }
   $.extend(targetObj, obj) // 默认浅拷贝
   targetObj.msg.age = 20;
   console.log(obj.msg.age) // > 20
   
   深拷贝：完全克隆，重新开辟 内存空间 存储 复杂数据类型
   $.extend(true, targetObj, obj) // 深拷贝
   targetObj.msg.age = 20;
   console.log(obj.msg.age) // > 18
   ```

   

### 24.18 多库共存

不同库内的==$==可能冲突

解决方法：

```javascript
使用jQuery代替$
jQuery("div").css("color", "#fff")
```

jQuery发生冲突时

解决方法：

```javascript
使用自定义名
var suibian = $.noConflict()
suibian("div").css("color", "#fff")
```



### 24.19 jQuery插件

1. 瀑布流
2. 懒加载

3. 全屏滚动：一次滚动一个屏幕
4. bootstrap3



## 25.做一个todolist

使用到的内容：本地存储、JSON.stringfy()、JSON.parse()

```javascript
JSON.stringfy() // 将参数转化为string型
JSON.parse() // 将字符串转化为javascript值或对象
```

## 26.数据可视化

一般使用百度开源的ECharts

### 26.1 ECharts使用步骤

1. 下载并引入echarts.js文件
2. 准备一个具有大小的DOM容器
3. 初始化echarts实例对象
4. 指定配置项和数据(option)
5. 将配置项给echarts实例对象

### 26.2 具体语法

1. title：标题

2. tooltip：提示框

   trigger: 触发方式，如item(鼠标经过部件)，axis(鼠标经过坐标轴触发)

   formatter: 将series中的信息附给提示信息

3. legend：图例

4. toolbox：工具栏

5. grid：绘图网格

   left、top、bottom、right表示边距

   containLable：true表示显示刻度标签，false表示隐藏刻度标签

6. xAxis：x轴

   type：数据类型

   ```javascript
   'value' 数值轴，连续，适用于连续数据
   'category' 类目轴，须通过data设置类目数据
   'time' 时间轴，连续，会根据时间跨度自动决定刻度标签的类型
   'log' 对数轴，适用于对数数据
   ```

   boundaryGap：坐标轴两边留白策略，表示标签与刻度的间隔

   ```javascript
   true 表示两边留白， false 表示两边不留白
   还可以用数值或百分比表示，如
   boundaryGap: ['20%', '20%']
   ```

7. series：系列，通过系列type决定使用的系列使用的类型

   ```javascript
   name: 系列名称，必须name和legend的data相同时，才会产生legend
   type：系列类型，如'line','pie','bar'等
   data: 数据
   	饼状图：[{value:5, name: "rose1"},{value:10, name: "rose2"}]
   
   //折线图
   stack: 数据堆叠，若设置同样的stack，则后续的数据值会叠加上前面的数据值
   
   //饼形图
   radius: 饼形图半径,radius[10, 50] 分别表示内径10px、外径50px，也可以是百分比
   center: 饼形图中心的定位，center['50%', '50%']表示在容器中心
   rosetype: "area"表示以面积显示，"radius"表示以半径显示
   
   label: {
       fontsize: 设置文字大小，值是纯数字
   }
   
   labelLine: { // 引导线
       length: 第一条线长度，纯数字,
       length2: 第二条线长度，纯数字
   }
   ```

   

8. color：表示各系列的线、扇形或图使用的颜色



### 26.3 做一个可视化项目

1. css3新增属性 边框图片：border-image

   九宫格：把四个角切图切出去，中间部分可以铺排、拉伸或环绕

   用代码切图：上、右、下、左按顺序

   语法：

   | 属性                | 描述                                                        |
   | ------------------- | ----------------------------------------------------------- |
   | border-image-source | 边框图片路径                                                |
   | border-image-slice  | 图片边框向内偏移量（不带单位，上右下左）                    |
   | border-image-width  | 图片边框宽度(带单位，是边框图片的宽度，使其不挤压其他内容)  |
   | border-image-repeat | 图像边框是否应平铺(repeat)、铺满(round)或拉伸(stretch,默认) |

   

2. 边框图片的设置

   切完图后，用一个innerbox，使用绝对定位，并用负数将box覆盖大边框层，数值应与slice一致

   ```css
   position: absolute;
   left: -30px;
   right: -30px;
   bottom: -30px;
   top: -30px
   ```

   最后给innerbox加上边距padding，编写内容

3. 通过类名调用字体图标

   HTML页面引入字体图标中css文件(style.css)

   用class直接调用字体图标

4. 引入多个ECharts

   使用立即执行函数

   ```javascript
   (function() {})();
   ```

   

5. 无缝滚动：

   先克隆marquee里面所有的行

   ```javascript
   $(this).append($(this).children().clone());
   ```

   

   通过CSS3动画滚动marquee

   ```css
   @keyframes move {
       0% {}
       100% {
           transform:translate(-50%)
       }
   };
   transition:move 15s linear infinite;
   ```

   

   鼠标经过marquees就停止动画（hover）

   ```css
   .marquee:hover {
       animation-play-state: paused;
   }



6. 修饰饼状图文字大小和引导线长短

   
