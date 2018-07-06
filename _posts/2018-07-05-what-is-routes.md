---
layout: post
title:  "什么是‘路由’"
date:   2018-07-26 11:08:08 +0800
categories: rails route 路由 restful REST 教程 学习 经验
---

“**路由**”是个外来词，应该是英文“route”的音译吧。
柯林斯词典里的解释是:
>+ A route is a way from one place to another.
>+ A bus, air, or shipping route is the way between two places along which buses, planes, or ships travel regularly.
>+ You can refer to a way of achieving something as a route .
>+ If vehicles, goods, or passengers are routed in a particular direction, they are made to travel in that direction.
>+ If telephone calls or other electronic signals are routed in a particular way, the signals are sent through a particular series of connections.

感觉就是具体的道路的抽象。也可以指电话和电子信号。既可以是名词也可以当动词用。

## `route` 命令

route命令用来显示并设置Linux内核中的网络路由表，route命令设置的路由主要是静态路由。要实现两个不同的子网之间的通信，需要一台连接两个网络的路由器，或者同时位于两个网络的网关来实现。

## 网络工程术语 routing
百度百科里的解释：
>路由（routing）是指分组从源到目的地时，决定端到端路径的网络范围的进程 。路由工作在OSI参考模型第三层——网络层的数据包转发设备。路由器通过转发数据包来实现网络互连。虽然路由器可以支持多种协议（如TCP/IP、IPX/SPX、AppleTalk等协议），但是在我国绝大多数路由器运行TCP/IP协议。路由器通常连接两个或多个由IP子网或点到点协议标识的逻辑端口，至少拥有1个物理端口。路由器根据收到数据包中的网络层地址以及路由器内部维护的路由表决定输出端口以及下一跳地址，并且重写链路层数据包头实现转发数据包。路由器通过动态维护路由表来反映当前的网络拓扑，并通过网络上其他路由器交换路由和链路信息来维护路由表。

## router 路由器
百度百科里的解释
>路由器（Router），是连接因特网中各局域网、广域网的设备，它会根据信道的情况自动选择和设定路由，以最佳路径，按前后顺序发送信号。 路由器是互联网络的枢纽，"交通警察"。目前路由器已经广泛应用于各行各业，各种不同档次的产品已成为实现各种骨干网内部连接、骨干网间互联和骨干网与互联网互联互通业务的主力军。路由和交换机之间的主要区别就是交换机发生在OSI参考模型第二层（数据链路层），而路由发生在第三层，即网络层。这一区别决定了路由和交换机在移动信息的过程中需使用不同的控制信息，所以说两者实现各自功能的方式是不同的。
>路由器（Router）又称网关设备（Gateway）是用于连接多个逻辑上分开的网络，所谓逻辑网络是代表一个单独的网络或者一个子网。当数据从一个子网传输到另一个子网时，可通过路由器的路由功能来完成。因此，路由器具有判断网络地址和选择IP路径的功能，它能在多网络互联环境中，建立灵活的连接，可用完全不同的数据分组和介质访问方法连接各种子网，路由器只接受源站或其他路由器的信息，属网络层的一种互联设备。

[维基](https://en.wikipedia.org/wiki/Router_(computing))的解释：
>A router is a networking device that forwards data packets between computer networks. Routers perform the traffic directing functions on the Internet. Data sent through the internet, such as a web page or email, is in the form of data packets. A packet is typically forwarded from one router to another router through the networks that constitute an internetwork until it reaches its destination node.
A router is connected to two or more data lines from different networks. When a data packet comes in on one of the lines, the router reads the network address information in the packet to determine the ultimate destination. Then, using information in its routing table or routing policy, it directs the packet to the next network on its journey.


## Ruby on Rails 里的 `route`

官方文档专门有[一篇文章](http://guides.rubyonrails.org/routing.html)来介绍路由的使用。文章很长，我也没有仔细读过。
最近在看这本书“Engineering long-lasting software: an agile approach using SaaS and cloud computing”, 书中的解释很好，是这样说的：
>在MVC模式下，用户发出的CRUD请求由控制器负责处理, 在rails中，这些请求都由控制器里的方法负责处理。因此，每个HTTP传入请求必须被映射到相应的控制器和控制器里特定的方法上。这个映射称为路由。

代码大概是这个样子的：
```ruby
  root 'movies#index'

  # Example of regular route:
     get 'products/:id' => 'catalog#view'

  # Example of named route that can be invoked with purchase_url(id: product.id)
     get 'products/:id/purchase' => 'catalog#purchase', as: :purchase

  # Example resource route (maps HTTP verbs to controller actions automatically):
   resources :movies

```
一个路由将一个URI加上HTTP方法与特定的控制器(Controller)和方法(Action)连接起来。 **REST**将各种Web应用程序操作的实体看作为资源，而不是网页、网站、链接什么的。这样设计的路由，让HTTP请求就可以包含资源和行为的所有必要信息。因此特别适合SaaS的体系结构。

## Express on Nodejs
todo
## Reactjs
😱🙀前端也有路由！！
todo
## Vuejs
todo
