# 爬虫技术栈集合


## 1.Python网络编程
### 1.1 Python基础
### 1.2 Python进阶






## 2.JS网页逆向编程
```
JS的三大块：
    1. ECMA标准语法（最重要）
    2. DOM
    3. BOM
 
 
ECMA标准语法：
1. 解释型语言或者编译型语言
   JS是一个解释型语言，需要解释器，浏览器是解释器
2. 变量
3. 数据类型（基本数据类型，容器类型）
4. 运算符
5. 流程控制语句（分支+循环）
6. 函数
```
### 2.1 JS语法
#### 2.1.1 JS的引入方法
1.外部js引入
2.script标签引入
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        h3 {
            color: rebeccapurple;
            font-style: italic;
        }
    </style>
</head>
<body>
<h3>hello JavaScript!</h3>
<script>
   dom = document.getElementsByTagName("h3")[0]
    dom.onclick = function () {
        alert(123)
    }
</script>
<!--<script src="index.js"></script>-->
</body>
</html>
```
#### 2.1.2 JS的变量
1.undefined
```
var x
console.log(x)
```
2.变量赋值
```
var x
x = 100
console.log(x)
```
3.声明并赋值
```
var y = 200;
console.log(y)
```
4.一次性可以声明多个变量
```
var name="yuan", age=20, job="lecturer";
var a, b, c=3, d, e = 5;
console.log(a,b,d) --》undefined undefined undefined
console.log(c,e) ---》3 5
```
#### 2.1.3 JS的数据类型
#### 2.1.4 JS的运算符


