title: 客官，快来Hapi 啊～
author: Gosthand
tags:
  - Hapi
  - Node
categories:
  - Node框架
date: 2018-12-17 07:35:00
---
# 客官，快来Hapi啊～

## about hapi
hapi是node框架中一个易于使用的以<b><i>配置</i></b>为中心的框架，内置支持输入验证，缓存，身份验证以及用于构建Web和服务应用程序的其他基本工具。hapi使开发人员能够专注于以高度模块化和规范性的方式编写可重用的应用程序逻辑。

Hapi使用插件来扩展其功能。插件在运行时通过代码进行配置。有各种各样的Hapi插件，其功能包括路由，身份验证，日志记录等等。

<!--more-->

## hapi install
```shell
mkdir my-hapi-project
cd my-hapi-project
npm init
npm install --save hapi@x.x.x
# 以上命令将会安装hapi,并将相应的依赖保存至package.json中
```

## hello word in hapi
### 创建一个Web服务器
```node
'use strict';

const Hapi = require('hapi'); //引入hapi
const server = Hapi.server({  //创建器并配置监听端口
    port: 3000,
    host: 'localhost'
});
//创建路由
server.route({
    method: 'GET',
    path: '/',
    handler: (request, h) => {
        return 'Hello, world!';
    }
});
server.route({
    method: 'GET',
    path: '/{name}',
    handler: (request, h) => {
        return 'Hello, ' + encodeURIComponent(request.params.name) + '!';
    }
});
//启动服务并打印日志,未集成日志插件
const init = async () => {
	await server.register(require('inert'));
    
    server.route({
        method: 'GET',
        path: '/hello',
        handler: (request, h) => {
            return h.file('./public/hello.html');
        }
    });
    
    await server.start();
    console.log(`Server running at: ${server.info.uri}`);
};
process.on('unhandledRejection', (err) => {
    console.log(err);
    process.exit(1);
});
init();
```