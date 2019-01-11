title: RPC 、REST、Webhooks、GraphQL
author: Gosthand
tags:
  - GraphQL
  - REST
  - PRC
  - Webhooks
categories:
  - 框架
date: 2019-01-11 02:58:00
---
## 写在前面
最近在研究一个项目、一个基于阿里最近开源的Fusion的项目,api我们想要采用GraphQL的模式来开发，说实在的GraphQL我们接触的并不是很多，因此只能寻找各种渠道先来了解GraphQL是个什么东东.网上偶然看了一篇 RPC vs REST vs GraphQL 的文章。突然想到或许我应该要写一些东西了。于是有了这篇文章，当然，其中会有借鉴部分结合个人的理解。若涉及版权问题请联系本人，谢谢！
<!--more-->
## RPC
说起RPC应该有很多人听说过gRPC。那么先来说说这两个名词吧


### 什么是RPC
RPC(Remote Procedure Call)是远程过程调用，比如说现在有两台服务器A, B，一个在A服务器上的应用想要调用B服务器上的应用提供的某个方法，由于不在两个方法不在一个内存空间，不能直接调用，需要通过网络表达调用的语义和传达调用的数据。此模式常存在于分布式系统中。

简单来讲， RPC 指的就是一个进程（ client ）发起一个函数调用，但是实际用来执行这个函数调用是另一个进程（ server ）。这个函数调用会阻塞在那里，直到收到响应。 Server 进程可以与 client 进程可以位于同一台机器也可以是不同机器。 Client 和 server 都有一个 stub 模块， client 的 stub 负责发送 request ，并处理 server 返回的 response ；而 server 的 stub 则负责处理 client 发送的 request ，并返回 response 。 通常，我们使用 `Interface Description Language` 来定义 RPC 的消息格式。

`RPC的本质是提供了一种轻量无感知的跨进程通信的方式`。在分布式机器上调用其他方法与本地调用无异（远程调用的过程是透明的，你并不知道这个调用的方法是部署在哪里，通过PRC能够解耦服务）。RPC是根据语言的API来定义的，而不是基于网络的应用来定义的，调用更方便，协议私密更安全、内容更小效率更高。

http接口是在接口不多、系统与系统交互较少的情况下，解决信息孤岛初期常使用的一种通信手段；优点就是简单、直接、开发方便。利用现成的http协议 进行传输。但是如果是一个大型的网站，内部子系统较多、接口非常多的情况下，RPC框架的好处就显示出来了，首先（基于TCP协议的情况下）就是长链接，不必每次通信都要像http 一样去3次握手什么的，减少了网络开销；其次就是RPC框架一般都有注册中心，有丰富的监控管理；发布、下线接口、动态扩展等，对调用方来说是无感知、统 一化的操作。第三个来说就是安全性。最后就是最近流行的服务化架构、服务化治理，RPC框架是一个强力的支撑。


### 什么是gRPC
所谓的gRPC就是goole的RPC实现。其默认使用 `protocol buffers`,下图是一个使用gRPC的例子（图出自 [Getting started ](http://www.grpc.io/docs/) ）：

![upload successful](/images/image.png)

## REST
REST表示的是`描述性状态传递(representational state transfer)`,REST 应该是我们最常见的、最通用的接口设计方案。

REST规范把所有内容都视为资源，网络上一切皆资源。
## Webhooks
## GraphQL