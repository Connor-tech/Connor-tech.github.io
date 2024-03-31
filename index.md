# 1. Python基础



## 1.1 break和continue



# 2. web基础

## 2.1 http



## 2.2 刷新抓包



## 2.3 表单请求和ajax请求

当看到页面上有一个表单时，当输入账号+点击登录/注册提交，数据提交就两种方式：

》表单提交，特征：提交数据页面刷新

```
<form action:"https://www.xxxx.com/login" method='post'>
	<input type='text' name='user'/>
	<input type='text' name='password'/>
```



》ajax提交，特征：提交页面不刷新，“偷偷”提交。







# 3. 前端

## 3.1 前端之HTML



## 3.2 前端之CSS



## 3.3 前端之JavaScript

### 3.3.1 JavaScript基础

#### 3.3.1.1  js代码执行顺序

```
依赖于HTML，从上往下执行
```

![image-20240121112717078](C:/Users/huwen/AppData/Roaming/Typora/typora-user-images/image-20240121112717078.png)



#### 3.3.1.2  js基本数据类型

在js中主要有几种数据类型(基本)

```js
number	数字，不论整数还是小数，数据类型都是number
string	字符串，单纯的字符串
boolen	布尔值 小写true false
object	对象，比较特殊，可以理解为所有被new出来的东西都是对象
underfined	这个表示未定义，所有没有被定义过的东西都是该类型	
控制台打印数据类型：console.log(typeof(变量));
```

js逆向中容易看到的一些恶心人的东西, 变量没有被赋值，往后面看一定是有赋值的

```js
var a, b=10, c, d=20;
```

// 如果+左右两端任意数据是字符串数据，结局就是字符串拼接

```js
var b = "10086"
console.log(b + 10) 
console.log(10 + b)
```

// 字符串变成number类型

```js
var b = "10086"
var c = parseInt(b)  // int(b) 将字符串转换为数字 parseFloat(b)
console.log(c + 5)
```

// number类型转为字符串

```js
d = 10086 
// 方案一.
f = d.toString()
console.log(typeof(f))
console.log(f)
// 方案二.野路子
f = d + ""
console.log(typeof(f))
console.log(f)
```

// 布尔类型

```js
var a = 3 < 2
console.log(a)  // true, false

// 逆向里面的涉及到布尔值的坑
// and, or,  not
// &&,	 ||,   !
console.log((3>2) || (1<5))
console.log((3>2) && (1<5))
console.log((3>2) ! (1<5))

// 等于比较
a = '10086'
b = 10086
console.log(a==b)	// 两个等号 == 表示判断两边的值
console.log(a===b)	// 三个等号 === 表示判断两端的值，同时还要判断数据类型

// 三元表达式
var a = 10
var b = 20
var c = a > b ? a : b    // 表达式1 ? 结果1 ：结果2  
逆向中写的老长老长了，只要找到 问号 和 冒号 就能知道逻辑关系。问号前面的整个执行下来就是判断个布尔值，
如果是真，那就是冒号前面的这个结果，如果为假，那就是冒号后面的结果。

// 复杂版
a = 10
b = 20
var c = a > b ? (a) : (b ? a : b)
console.log(c);
```

// object对象

```js
var arr = new Array()  // []
console.log(typeof(arr));
```

// ++ --运算

```js
var i = 10

// i ++; 让i自增1 i += 1
// ++ i; 让i自增1 i += 1

// i --; 让i自减1 i -= 1
// -- i; 让i自减1 i -= 1

// 只要涉及到赋值，i++ 的结果依然是 i ; ++i 的结果就是 i+1
var j = i ++;
var q = ++i;
console.log(j)
console.log(q)
```



#### 3.3.1.3 字符串操作

// 字符串切割

```js
var s = 'alex_wusir_sb'
// 切割
console.log(s.split("_"))  // 结果是列表
console.log(s.substring(3, 4))  // 从下边为3的地方开始切切到字符为5的地方但是不包括5，  substing(start, end)
```

// 字符串长度

```js
var s = 'alex_wusir_sb'
console.log(s.length)  // len(s) 
```

// 指定索引的字符

```js
var s = 'alex_wusir_sb'
console.log(s.charAt(3))  // s[3] 索引为3的字符
```

// 判断字符的索引

```js
var s = 'alex_wusir_sb'
console.log(s.indexof("wus"))  // 有的话返回下标索引
console.log(s.indexof("wus未sdfdssdf"))  // 没有的话返回 -1
// 所以indexof常被拿来用做判断
if s.indexof("xxxxx") == -1;
// 判断字符串在不在，还有一个
console.log(s.includes("wusir"))  // 返回true or false
```

// 转换为大写

```js
var s = 'alex_wusir_sb'
console.log(s.toUpperCase())  // 转换成大写
```

// 判断是否以xxx开头

```js
var s = 'alex_wusir_sb'
s.startsWith("xxx")  // 判断是否以xxx开头
```

// 关于null 和 undefined

```js
这两个很容易混淆，可以这样来记忆，null就是空对象，underfined就是空变量，两者都可以表示空，啥也没有，本质上其实都是一样的，都啥也干不了，两者都可以当做false来看待就好了。
```



#### 3.3.1.4 JS条件分支

除了HTML外，几乎所有的编程语言都有条件判断的功能，比如，python, 我们用if语句来做条件判断，到了javascript中也是一样的，也使用javascript来做条件上的判断。if switch 两个条件判断

```js
// 语法
if(条件1){
    代码块1
}
// 解读：当‘条件1’成立时，执行代码块1中的内容，如果‘条件1’不成立，则不执行该‘代码块1’中的内容
// 注，如果‘代码块1’中的内容只有一行，则可以省略外面的大括号(一些逆向工程里会有)
```

```js
<script>
    var a = 3;
	if(a>6)console.log("hahahaha")else console.log("呵呵")；
	if(a>5){
        console.log("比5都大")；
    }else{
        console.log("比5都小")
    }
</script>
```

// switch case穿透

```js
<script>
    const a = 3;
    switch(a){
        case 1:
            console.log("星期一")
            break;  // 为了防止case穿透的
        case 2:
            console.log("星期二")
            break;  // 为了防止case穿透的
        case 3:
            console.log("星期三")
            break;  // 为了防止case穿透的
        case 4:
            console.log("星期四")
            break;  // 为了防止case穿透的
        case 5:
            console.log("星期五")
            break;  // 为了防止case穿透的
        case 6:
            console.log("星期六")
            break;  // 为了防止case穿透的
        case 7:
            console.log("星期日");
            break;  // 为了防止case穿透的
    }
</script>
```

```js
case穿透有些情况避免代码重复  B站的逆向涉及到switch的 case穿透
```

```js
<script>
    var month = "一月";
    switch(month){
       case "一月"：
       case "二月"：
       case "三月"：
            console.log("第一个季度")；
            break;  // 为了防止case穿透的
            
       case "四月"：
       case "五月"： 
       case "六月"：
            console.log("第二个季度")；
            break;  // 为了防止case穿透的  
            
       case "七月"：
       case "八月"： 
       case "九月"：
            console.log("第三个季度")；
            break;  // 为了防止case穿透的  
            
       case "十月"：
       case "十一月"： 
       case "十二月"：
            console.log("第四个季度")；
            break;  // 为了防止case穿透的  
    }
</script>
```

#### 3.3.1.5 js循环语句

// while 循环

```javascript
let i = 1;
while(i<=10){
    console.log(i);
    i++;
}
```

// do...while

```javascript
let i = 1;
do {
    console.log(i)
    i++;
}while (i<=10)
do...while由于是先执行的循环体，所以，至少会执行一次循环体的内容，哪怕条件是假的
```

// for 循环

**第一种写法：**

```js
for (初始化表达式; 条件表达式；改变循环变量的表达式){
	循环体
}
```

![image-20240330205608949](C:/Users/huwen/AppData/Roaming/Typora/typora-user-images/image-20240330205608949.png)

* 1.初始化表达式
* 2.判断条件 --> 当条件为假，循环结束
* 3.执行循环体
* 4.改变循环变量
* 5.回到第二步

**第二种写法：**

```javascript
let arr= [11,22,33,44]
for(let ar in arr){  // 这样拿到的是索引，是数组下标。
    console.log(arr[ar])
}
```

```javascript
let wangfeng = {
    name: "汪峰",
    age: 18,
    gender: "male"
}
for (wang in wangfeng){
    console.log(wang)
}
```

```javascript
列表特有的一个方案
let arr=[11,22,33,44]
arr.forEach(  // 让arr中的每一个去执行一次里面的函数，把被循环的内容一个一个的传递给函数
    function (item){
        console.log(item)
    }
)
```

#### 3.3.1.6 数组和对象

// 数组

```javascript
let arr=[11,22,33,44]
for (let i=0;i<arr.length; i++){
    console.log(arr[i]);
}
```

```javascript
let p ={
    name: "汪峰",
    age: 18,
    gender: "male",
    chi: function (){
        console.log("吃饭")  // 返回值是一个underfined
    }
}
console.log(p['name'])
console.log(p['age'])
console.log(p['gender'])
console.log(p.chi())  // 执行chi函数
或者 console.log(p['chi']()) 这种执行chi函数也没有问题
```



#### 3.3.1.7 JS函数

// 有名函数

```javascript
let a = function(){
	console.log("我爱黎明")
}
a()
这个a可以是除了数字的各种符号，比如_,比如 $，其他的js语法如何不支持也不行，请知悉。
```

// 匿名函数or叫自执行函数

在前端: 除了数字，任何东西都可以后面加小括号()，任何东西必须得是函数

```
()()
第一个小括号里面必须是一个函数，可以写成下面的样式，浏览器渲染的时候就直接加载出来。这种没有函数名，无需调用。
(function (a,b){
    console.log(a+b)
})(1,3)
```

![image-20240330222413202](C:/Users/huwen/AppData/Roaming/Typora/typora-user-images/image-20240330222413202.png)

复杂版函数

```javascript
c = (function (){
    let m ={
        name: "佩奇",
        age:18,
        xijiao:function (a){
            console.log(a+"来帮我洗脚");
        }
    }
    return m
})()
// 取名字
console.log(c['name'])   // 佩奇
console.log(c['age'])   // 18
console.log(c['xijiao']('alex'))  // alex来帮我洗脚  undefined
console.log(c.xijiao('葛俊杰'))   // 葛俊杰来帮我洗脚  undefined
```



### 3.3.2 JavaScript进阶



#### 3.3.2.1 定时器

// 第一种方法：setTimeout 定时器设置与清除

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<script>
    // 定时器
    let t= setTimeout(function (){
        console.log(8888)
    }, 3000)
    window.clearTimeout(t)
    alert("定时内容清理掉了")
</script>
</body>
</html>
```

// 第二种方法：setInterval每隔多少秒执行函数

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<script>
    // 定时器setInternal: 
    let t = setInterval(function (){
        alert("你吓到我！！！")
    }, 1000)
    // 清除定时器
    window.clearInterval(t)
    alert('定时器内容被清理掉了，呜呜呜~~')
</script>
</body>
</html>
```

**//// 定时器反爬案例**

使用setInterval每隔1微妙时间在函数执行体中不断写入浏览器的缓存导致浏览器卡住

```javascript
// 定时器setInternal: 
    let t = setInterval(function (){
        alert("你吓到我！！！")
        // 往来浏览器缓存里疯狂的写入数据
        xxxx
    }, 1000)
    // 解决方案：清除定时器
    window.clearInterval(t)
    alert('定时器内容被清理掉了，呜呜呜~~')
```



#### 3.3.2.2 时间

前端想格式一个时间，需要先定好一个格式

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<script>
    function fn(){
        // 时间
        let t = new Date()
        let year = t.getFullYear()  // 获取正常的年份
        // console.log(year)
        // 年份后面需要加上1
        let month = t.getUTCMonth() + 1  // 获取正常的月份
        // console.log(month)
        // 日期
        let date = t.getUTCDate()  // 获取到正常的日期
        // console.log(date)
        // 时
        let hour = t.getHours()  // 获取到正常的小时
        // console.log(hour)
        // 分
        let minute = t.getMinutes()  // 获取到正常的分钟
        // console.log(minute)
        // 秒
        let second = t.getSeconds()  // 获取到正常的秒
        // console.log(second)
        console.log(year + "_" + month + "_" + date + "_" + hour + "_" + minute + "_" + second);
    }
    // 设置一个定时器每隔1秒钟打印下时间：年月日时分秒
    setInterval(fn, 1000)
</script>
</body>
</html>
```

![image-20240331092123126](C:/Users/huwen/AppData/Roaming/Typora/typora-user-images/image-20240331092123126.png)

// 一般前端，如果不需要向用户展示的话，没有必要去格式化这个时间

// 时间戳（各个语言通用）

```javascript
let now = new Date()
console.log(now.getTime())  // 输出的是毫秒  要算秒再除以1000
```



#### 3.3.2.3 eval函数

eval函数是用来执行字符串函数的

加密网站：https://51tools.info/js/

```javascript
let s = 'console.log(999)'
eval(s)
```

![image-20240331095305324](C:/Users/huwen/AppData/Roaming/Typora/typora-user-images/image-20240331095305324.png)

如何破解？？？

打开具体的网站页面F12-给eval函数里面的参数自定义一个变量，然后在控制台输出该变量即可，如下图

![image-20240331095540029](C:/Users/huwen/AppData/Roaming/Typora/typora-user-images/image-20240331095540029.png)

或者使用第三方网站去解密eval加密的字符串函数

小tips: 如何格式化代码？ 快捷键：ctrl+Alt+L 或者在code-Reformate Code



#### 3.3.2.4 prototype

prototype是js里面给类增加功能扩展的一种模式。

// 1.先定义一个类

```javascript
function Person(name,age){
    // 属性，this表示当前人
    this.name = name;
    this.age = age;
    // 动作
    this.chi = function(fan){
        console.log(this.name + "在吃" + fan);
    	}
	}
	p1 = new Person("张无忌", 18)
	p2 = new Person("赵敏", 16)
	p2.chi("吴佩奇的脑袋")
```

// 2.给类追加一个功能

我现在代码写完了，突然之间，我感觉好像少了个功能，人不应该就一个功能，光会吃是不够的，还得能够ooxx,怎么办？直接改代码？可以但是不够好，如果这个类不是我写的呢？随便改别人代码是很不礼貌的，也很容易出错，怎么办？我们可以在我们自己代码中对某个类型动态增加功能，此时就用到了prototype.

```	javascript
<script>
    // 这就是类，person就是类名，对某一类事物的归纳总结
    function Person(name,age){
        // 属性，this表示当前人
        this.name = name;
        this.age = age;
        // 动作
        this.chi = function(fan){
            console.log(this.name + "在吃" + fan);
        }
    }
    // 动态给person这个类增加功能
    Person.prototype.xxoo = function (withwho){
        console.log(this.name + "和" + withwho + "在逛街")
    }
    p1 = new Person("张无忌", 18)
    // p2 = new Person("赵敏", 16)
    p1.xxoo('赵敏')
</script>
```



#### 3.3.2.5 变量提升





















# 4. 数据解析

## 4.1 xpath



# 5. Selenium



## 5.1 selenium入门



## 5.2 selenium进阶



# 6. 并发爬虫

## 6.1 异步协程

# 7.数据库

## 7.1 mysql

## 7.2 redis

## 7.2 mongodb

### 7.2.1 mongodb下载

下载地址：https://www.mongodb.com/try/download/community

安装Mongoshell，MongoDB6之前shell是直接在里面的6之后需要单独下载

mongoDB6没有mong.exe和mongdb.exe，要想通过命令行启动mongoDB需要自己下载一个Mongoshell，下载地址MongoDB Shell Download，直接下载即可 https://www.mongodb.com/try/download/shell

原文链接：https://blog.csdn.net/weixin_51293984/article/details/128076353

```
打开cmd或者powershell, 输入 mongosh即可进入mongodb数据库
```



### 7.3.2 mongodb的简单操作

```
db: 当前正在使用的数据库
```

// 创建数据库

```
use 数据库名
# 随意插入一条数据就创建了
db.a.insertOne({})
```

// 删除数据库

```
在当前数据库下，使用db.dropDatabase
```











# 8. Scrapy框架

## 8.1 scrapy初步介绍和使用

## 8.2 scrapy管道

## 8.3 scrapy模拟登录和中间件

## 8.4 。。。



# 9. 加密算法

夜幕视频



# 10.视频爬虫



