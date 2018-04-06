## 预备知识

- HTML
- CSS
- JavaScript
- 掌握基本的命令行操作
- 具有服务端开发经验更佳

---

## 安装 Node 环境

- 下载：https://nodejs.org/en/download/
  - 历史版本：https://nodejs.org/en/download/releases/
- 安装
  - 傻瓜式的一路 `next` 就可以了
  - 对于已经装过的，重新安装就会升级
- 确认 Node 环境是否安装成功
  - 打开命令行，输入 `node --version`
  - 或者 `node -v`

---

## REPL

- read
- eval
- print
- loop

类似于浏览器中的 Console ，可以做一些代码测试。

---

## Hello World

**1. 新建一个 hello.js 并写入以下示例代码**

```javascript
var message = 'Hello Node.js!'
console.log(message)
```

**2. 打开命令行并定位到 `hello.js` 文件所属目录**

**3. 在命令行中输入 `node hello.js` 回车执行**

> 注意：
> - 文件名不要起名为 `node.js`
> - 文件名或者文件路径最好不要有中文
> - 文件路径或者文件名不要出现空格

---

## 文件读写

文件读取：

```javascript
const fs = require('fs')

fs.readFile('/etc/passwd', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

文件写入：

```javascript
const fs = require('fs')

fs.writeFile('message.txt', 'Hello Node.js', (err) => {
  if (err) throw err;
  console.log('The file has been saved!');
});
```

---

## HTTP 服务

```javascript
// 接下来，我们要干一件使用 Node 很有成就感的一件事儿
// 你可以使用 Node 非常轻松的构建一个 Web 服务器
// 在 Node 中专门提供了一个核心模块：http
// http 这个模块的职责就是帮你创建编写服务器的

// 1. 加载 http 核心模块
var http = require('http')

// 2. 使用 http.createServer() 方法创建一个 Web 服务器
//    返回一个 Server 实例
var server = http.createServer()

// 3. 服务器要干嘛？
//    提供服务：对 数据的服务
//    发请求
//    接收请求
//    处理请求
//    给个反馈（发送响应）
//    注册 request 请求事件
//    当客户端请求过来，就会自动触发服务器的 request 请求事件，然后执行第二个参数：回调处理函数
server.on('request', function () {
  res.end('Hello Node.js!')
})

// 4. 绑定端口号，启动服务器
server.listen(3000, function () {
  console.log('服务器启动成功，请求访问 http://127.0.0.1:3000/')
})
```
