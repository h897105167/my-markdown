# Ajax

## 1. 典型应用场景

Ajax全称（Asynchronous javascript amd XML）；

XMLHttpRequest对象

用户名检测

搜索提示

数据分页、刷新表格

数据的增删改查操作



总结：网页与服务器的数据交互



## 2. jQuery中的Ajax

jQeury对XMLHttpRequest进行了封装，提供了一系列Ajax相关函数，极大降低了Ajax的使用难度

最常用的Ajax请求方法：

```javascript
$.get() 从服务器请求数据
$.post() 向服务器提交数据
$.ajax() 能请求数据或提交数据
```

### 2.1 $.get()

专门用来发起get请求

```javascript
$.get(url,[data],[callback])

url：string， 请求的资源地址 由通信协议、服务器名称、路径 组成
data：object，请求资源期间要携带的参数，发送给服务器
callback：function，请求成功时的回调函数
```

1. 发起不带参数的请求

   ```javascript
   $.get('http://www.liulongbin.top:3006/api/getbooks', function (res) {
       console.log(res) // res是服务器返回的数据
   })
   
   // 返回值
   {status: 200, msg: "获取图书列表成功", data: [{id: 1, bookname: "西游记", author: "吴承恩", publisher: "北京图书出版社"},…]}
   data: [{id: 1, bookname: "西游记", author: "吴承恩", publisher: "北京图书出版社"},…]
   msg: "获取图书列表成功"
   status: 200 // 200是返回成功的意思
   ```

   

2. 发起带参数的请求

   ```javascript
   $.get('http://www.liulongbin.top:3006/api/getbooks', { id: 1 }, function (res) {
       console.log(res) // res是服务器返回的数据
   })
   //{ id: 1 }是一个参数，表明指定返回对应id的值
   
   // 返回值
   {status: 200, msg: "获取图书列表成功", data: [{id: 1, bookname: "西游记", author: "吴承恩", publisher: "北京图书出版社"}]}
   data: [{id: 1, bookname: "西游记", author: "吴承恩", publisher: "北京图书出版社"}]
   msg: "获取图书列表成功"
   status: 200
   ```

   

### 2.2 $.post()

```javascript
$.post(url,data,[callback])

url: 提交数据的地址
```



### 2.3 $.ajax()

基本语法

```javascript
$.ajax({
    type: '', // 请求方式，如GET或POST
    url: '', // 请求的url地址
    data: {}, // 请求携带的参数，可省略
    success: function(res) {} // 请求成功后的回调函数
})
```

1. 使用$.ajax()发起get请求

   ```javascript
   $.ajax({
       type: 'GET', 
       url: 'http://www.liulongbin.top:3006/api/getbooks', // 请求的url地址
       data: { id:1 }, // 请求携带的参数
       success: function(res) {
           console.log(res)
       }
   })
   ```

2. 使用$.ajax()发起post请求

   ```javascript
   $.ajax({
       type: 'POST', 
       url: 'http://www.liulongbin.top:3006/api/addbooks', // 请求的url地址
       data: { 
           name: '水浒传',
           author: '施耐庵',
           publisher: '天津图书出版社'
       }, 
       success: function(res) {
           console.log(res)
       }
   })
   ```

   

### 2.4 接口

​	使用Ajax请求数据时，被请求的URL地址就叫做数据接口(简称==接口==)。每个接口都有不同请求方式。如

```javascript
'http://www.liulongbin.top:3006/api/getbooks' // 获取图书列表接口(GET请求)
'http://www.liulongbin.top:3006/api/addbooks' // 添加图书的接口(POST请求)
```

### 2.5 接口测试工具Postman

能在不写任何代码的情况下，对接口进行调用和测试

推荐使用edge插件==postwoman==或者vscode插件==postcode==

![image-20230301111757157](C:\Users\PC\AppData\Roaming\Typora\typora-user-images\image-20230301111757157.png)

### 2.6 接口文档

如何使用接口的说明文档，是调用接口的依据

接口URL、参数以及输出内容的说明

1. 组成

   （1）接口名称：功能的简单说明，如登录接口、图书列表接口等

   （2）接口URL：接口的调用地址

   （3）调用方式：如GET或POST

   （4）参数格式：参数名称、参数类型、是否必选、参数说明

   （5）相应格式：返回值的描述：数据名称、数据类型、说明

   （6）返回示例(可选)：通过对象形式，例举服务器返回数据的结构



### 2.7 示例：图书管理系统

1. 使用bootstrap3和jquery进行代码编写

```html
<!-- 这里用bootstrap3直接调出panel-primary -->
<div class="panel panel-primary">     
    <div class="panel-heading">
        <h3 class="panel-title">添加新图书</h3>
    </div>
    <div class="panel-body form-inline">

        <!-- 这里用bootstrap3直接调出input-group-addon -->
        <div class="input-group">
            <div class="input-group-addon">书名</div>
            <input type="text" class="form-control" id="iptBookname" placeholder="请输入书名">
        </div>

        <div class="input-group">
            <div class="input-group-addon">作者</div>
            <input type="text" class="form-control" id="iptAuthor" placeholder="请输入作者">
        </div>

        <div class="input-group">
            <div class="input-group-addon">出版社</div>
            <input type="text" class="form-control" id="iptPublisher" placeholder="请输入出版社">
        </div>
		<!-- 这里用bootstrap3直接调出btn-primary -->
        <button id="btnAdd" class="btn btn-primary">添加</button>

    </div>
</div>

<!-- 这里直接用table-bordered -->
<table class="table table-bordered table-hover">
    <thead>
        <tr>
            <th>id</th>
            <th>书名</th>
            <th>作者</th>
            <th>出版社</th>
            <th>操作</th>
        </tr>
    </thead>
    <tbody id="bookBody">
    </tbody>
</table>
```



js部分

```javascript
$(function () {    
    function getBookList() {
        $.get('http://www.liulongbin.top:3006/api/getbooks', function (res) {
            if (res.status !== 200) {
                return alert('获取图书列表失败！');
            }
            var rows = [];
            $.each(res.data, function (i, item) {
                rows.push('<tr><td>' + item.id + '</td><td>' + item.bookname + '</td><td>' + item.author + '</td><td>' + item.publisher + '</td><td><a href="javascript:;" class="del" data-id="' + item.id + '">删除</a></td></tr>');
            })
            // 使用join方法和append方法，也可以使用tostring()和html()
            $("#bookBody").empty().append(rows.join(''))
        })
    }
    // 预加载
    getBookList();

    // 删除代码，有待补充
    $('tbody').on('click', '.del', function () {
        var id = $(this).attr('data-id')
        })
})

// 添加书籍，非常简单
$('#btnAdd').on("click", function () {
    var bookname = $("#iptBookname").val().trim(); // trim去除两端空格
    var author = $("#iptAuthor").val().trim();
    var publisher = $("#iptPublisher").val().trim();
    if (!bookname || !author || !publisher) {
        return alert('请填写完整信息！')
    }
    $.post('http://www.liulongbin.top:3006/api/addbooks', { bookname: bookname, author: author, publisher: publisher }, function (res) {
        if (res.status !== 201) {
            return alert('添加失败！')
        }
    })
    getBookList();
    $("#iptBookname").empty();
    $("#iptAuthor").empty();
    $("#iptPublisher").empty()
})
```



### 2.8 聊天机器人
