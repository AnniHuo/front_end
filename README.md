# 学习步骤

### 一.学前准备

1.请确保电脑中装有如下编译器其中之一:webstorm,vscode,sublime text

2.请先学会如何进入浏览器开发者工具(非常重要的技能！脉策工作必备技能！)

3.如果仅有python编程基础，在学习的过程中请先忘记一些概念和用法，因为不适合类比。
比如：类，面向对象，pandas，列表，字典.....和一些习以为常的功能，len(), sort(),max().....

4.在学习过程中，记住两句话，可以提高学习成功率：

万物皆方块

函数是一等公民

### 二.先观察

1.在class_10文件夹中，先打开index.html,这是一个Geocoding工具，请先简单体验下页面功能。

![](demo.gif)

2.用代码编辑器打开index.html,观察代码结构。通常情况下，一份最简单且完整的前端脚本结构如下：

```html
<!DOCTYPE html>
<html>
<head>
    <style></style>
    <script></script>
</head>
<body></body>
<script></script>
</html>
```
head: 里面通常会引入页面相关的样式，脚本和标注一些基本信息

style: 定义了页面的样式

body: 主要定义页面结构

script: 页面的交互逻辑(javascript代码),可以定义在脚本任意位置，代码会按顺序执行。
通常会定义在head中和body后(思考这是为什么？)

**知识点：**

下面这种结构叫标签(tag)，不同的标签代表不同的页面元素，标签与标签之间通过嵌套阐述页面之间的关系
```html
<xxx></xxx>
<xxx />
```
通常绝大多数标签由开标签和闭标签组成，也有少数标签没有结束标签
```html
<div></div>
<span></span>
<button></button>

<input type="text" />
<input type="password" />
<br />
```
*练习：请百度上述提到的标签，并了解这些标签的功能*

*练习：用代码编辑器创建一个后缀为.html的文件，
并参考index.html脚本head中的style标签中的样式书写方式，
在body中画一个长100px,宽100px，红色的正方形*


### 三.结构与样式
1.一个完整的前端由三部分组成,结构(html)，样式(css)，交互(javascript)组成。
结构相当于房子的户型，样式类比于装修，而交互就好比家里的小米扫地机器人。
没有装修的房子是毛坯房，没有样式的html是txt,
家里的卫生是用扫把解决还是用小米扫地机器人取决于javascript的代码编写能力

2.万物皆方块，所有的网页都是由方块组成的。

example:

![](页面结构拆解.png)

*练习：观察任意网站，并画出粗略的结构图*
   
3.万物皆方块，而每个方块可以有边距，边框和填充。

*练习：请百度什么是CSS盒模型*
   
4.在结构与样式的编写中，div标签几乎可以代替95%其他的标签，所以如果不知道用哪个标签，使用div一般不会错。

5.CSS样式引入有三种方法，内联样式，嵌入式样式，外部样式

*练习：查阅资料，并在index.html中找到内联样式和嵌入式样式*

### *单元练习*
1.熟悉常用的css样式:

width,height,margin,padding,border,border-radius,
background-color,color,display,font-size,font-weight

2.阅读，知道，并熟练掌握flex弹性布局
https://www.runoob.com/w3cnote/flex-grammar.html

<font color=YellowGreen size=10>请查阅前端布局基础练习.docx，并完成基础练习题</font>

3.参考google官网首页，并仿照官网自己写一个一样的，图中有许多logo，可以任意选一张图片代替。如果实在不知道如何在页面中引入图片，可以用div代替

![](google.png)

提示：

可能会用到的标签:div,input,img,span

可能会用到的样式:flex弹性布局,width,height,margin,background-color,color,border-radius,font-size

### 四.交互(javascript)

```javascript
// 打印，常用于开发时测试
console.log('hello world');

// 变量
var a = 1;
var b = '你好';
var c;
console.log(a);
console.log(b);

// 局部变量, 常用于函数中，为块级作用域
var a = 2;
{
    let a = 3; //局部变量
    console.log(a); // 3
}
console.log(a); // 2

// 常量 常量必须在定义的时候被赋值
const a = 1
console.log(a)

//重点：如果对于var, let, const应用不熟练，理解有困难，可以统一全部使用var

// 对象 
// 类似于python中的字典，java中的哈希映射。仅结构类似，功能不完全一致。
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
console.log(person['lastName']) // Doe

// 数组, 类似于python中的列表。仅结构类似，功能不完全一致。
var numbers = [1, 3, 5, 7, 9]
console.log(numbers[0]) // 1

// 运算符
// 算数运算符，与其他编程语言一致
// + - * / % ++ --
// 赋值运算符，与其他编程语言一致
// = += -= *= /= %=
// 比较运算符
// == 等于 ===全等于(值和类型都相等) !=不等于 !==不绝对等于
// > < >= <= 和其他编程语言一致
// 逻辑运算符
// && and
// || or
// ! not

// 字符串拼接
var a = '数字是';
var b = 1;
var c = "。"
console.log(a + b + c) // 数字是1。

// 条件判断
// if (condition1)
// {
//     当条件 1 为 true 时执行的代码
// }
// else if (condition2)
// {
//     当条件 2 为 true 时执行的代码
// }
// else
// {
//     当条件 1 和 条件 2 都不为 true 时执行的代码
// }
var a = '10';
if (a === 10){
    console.log("a是10")
}else if (a == 10) {
    console.log("a是10，a的类型不是10") //会打印这句
} else {
    console.log("a不是10")
}

// 循环
var cars=["BMW","Volvo","Saab","Ford"];
for (var i = 0; i < cars.length; i++){
    document.write(i); // 0 1 2 3
    document.write(cars[i] + "<br>"); //BMW, Volvo, Saab, Ford
}
// 对于列表比较简单的循环方法
cars.forEach((item, idx) => {
    console.log(item); //BMW, Volvo, Saab, Ford
    console.log(idx); // 0 1 2 3
})

// 函数 强烈推荐使用第三种写法
function add(a, b){
    return a + b;
}

var add = function (a, b){
    return a + b;
}

const add = (a, b) => {
    return a + b
}

// DOM 操作
// DOM: document object model 意思是网页的html
// 我们可以用js去控制html，比如增加内容，修改样式，增加点击事件等，从而达到网页交互的目的
// DOM的内容细节较多，不一一举例，可以去在线平台进行一些简单的尝试，https://www.runoob.com/js/js-htmldom.html
// 下面举例几个常用的例子，这些例子都可以在开头提到的样例脚本中找到具体的案例

// 根据html标签的Id获取这个标签
var obj = document.getElementById("btn")
// 对于某个标签绑定单击事件，事件内容为打印标签中的文本
obj.addEventListener("click", (e) => {
    console.log(e.target.innerText)
})

// 最为无脑的动态渲染页面的方法
// 假设有一个div，id是container(<div id="container"></div>)
// 我们要根据一个列表中的值在div中渲染span

var context = ['javascript', 'python', 'java', 'golang', 'ruby']
var html_str = ''
context.forEach(item => {
    html_str = html_str + "<span>" + item + "</span>"
})
var container = document.getElementById("container")
container.innerHTML = html_str
// result:
//     <div id="container">
//         <span>javascript</span>
//         <span>python</span>
//         <span>java</span>
//         <span>golang</span>
//         <span>ruby</span>
//     </div>

// 从服务器获取数据
// 通常前端页面展示的具体内容都是通过访问服务器接口得到的，JS也有些常用的包帮助我们从服务器获取数据
// 比如jQuery ajax; axios; fetch.....
// 下面介绍使用axios通过get请求从服务器获取数据，并异步打印的过程。
// http请求有很多种，get, post, put, delete, options.....
// 通常js访问接口，都是异步进行的

    axios.get("http://localhost:9800/pois", {
        headers: {
            'Access-Control-Allow-Origin': '*',
            'Content-Type': 'application/json',
        } // 这叫请求头，对一些基本的东西做些约定
    }).then((response) => {
        // 以下代码块执行的内容均为异步执行
        // 也就是通过axios获取数据后，对数据进行的一切操作的代码都必须写在这个代码块内
            console.log(response.data) // 打印接口获取的数据
        
        
        })
        .catch((error) => {
            // 接口获取数据有可能会失败，如果失败会执行下面的逻辑
            console.log(error);
        })
```
### 四.课程大作业

1. 课程不可能用20个小时的冗长视频事无巨细的把所有js知识点涵盖到位。所以，重在自身不断探索，不断学习。
   
2. 但是课程大作业中的知识点一定在课程案例脚本和本文档内。也就是说，仅仅凭借模仿，就能完成作业。
   
3. 在answer文件夹中有个index.html脚本，这是大作业的参考答案。

**步骤与要求：** 
1. 制作一个配套字典的展示页，如下图所示:

![](step1.gif)

2. 页面中的数据需通过接口访问服务器动态获取。本地启动模拟服务器的方法：

在assignment/backend/ 文件夹中有服务器运行文件，双击打开即可，windows打开api_windows.exe;mac打开api_mac

接口为get请求，地址为：http://localhost:9800/pois，可以在浏览器地址栏中测试服务器是否启动成功

![](step2.png)

3. 页面需在打开后得到接口数据并在页面按如图样式展示，点击更新按钮，会再次从接口获取数据，刷新页面内容

4. poi数量，大于等于10的以绿色显示，大于等于5的以蓝色展示，小于5的以红色展示。

5. 具体样式，颜色与截图类似即可，也允许查看参考答案，得到具体色号，长宽等内容。

6. 在作业中可能涉及的知识点：
   
    样式:
    
    flex弹性布局, background-color, color, border-radius, 
    
    font-size, width, height, border, cursor, margin
    
    接口访问:
    
    axios访问接口, 数组的循环(forEach), 对象内容的提取(obj['xxx'])
    
    DOM操作:
    
    document.getElementById('xxx'),
    
    obj.addEventListener('click', () => {})
    
    obj.innerHTML

7. 如果作业过程中需要引入除axios以外的js插件，可自行下载。

8. 鼓励在作业要求的基础上，添砖加瓦，增加更多的功能，展示自己的实力。

9. 完成作业后，以homework.html文件放置在assignment中，提交MR即可。
