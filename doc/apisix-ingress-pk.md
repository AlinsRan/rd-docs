---
title: "为什么 APISIX Ingress 是比 Ingress NGINX 更好的选择？"
description: "对比 APISIX Ingress 和 Ingress NGINX 之间有什么区别"
slug: 
category: Technology & Products
site:
  - api7.ai
tags:
  - Apache APISIX
  - Ingress
  - Kubernetes
keywords:
  - Apache APISIX
  - Ingress
  - Kubernetes
author_name: ""
author_avatar_url: ""
author_bio: ""
canonical_url: ""
cover_url: 
---


本文主要对比两个 Ingress Controller 竟品之间的差异。Ingress NGINX 是 Kubernetes 官方所推荐的默认 Ingress Controller 被大家广泛认知，其实现基于备受欢迎的 Nginx 平台而被大家广泛使用。那么 Ingress NGINX 有着什么样的痛点呢，为什么说 APISIX Ingress 是比 Ingress NGINX 更好的选择？

## APISIX Ingress vs Ingress Nginx

> 数据取自：<https://docs.google.com/spreadsheets/d/191WWNpjJ2za6-nbG4ZoUMXMpUK8KlCIosvQB0f-oq3k/edit?ts=5fd6c769#gid=907731238>

![背景](https://raw.githubusercontent.com/AlinsRan/rd-docs/main/images/apisix-ingress-vs-ingress-nginx.jpg)

通过上图，可以看到 APISIX Ingress 内置的功能和特性相比 Ingress NGINX 更加丰富，其中包括协议支持，认证鉴权，负载均衡算法等等，本文将具体介绍它们之间的差异。

## APISIX Ingress 支持更多的内置基本能力

### 更多协议支持

网络上的流量很容易被窃听，如果要传输敏感数据比如登陆密码，我们必须要加密，否则这些数据将被中间人一览无余。HTTP 协议可以通过 HTTPS 来进行加密，TLS 工作在 TCP 和 HTTP 协议之间，所以 TLS 可以加密 TCP 流量。而 APISIX 就支持使用 TLS 加密 TCP 流量。

### 完善的服务治理能力

#### 健康检查

APISIX Ingress 支持健康检查（主动和被动），确保应用 pod 的可用性。

* 主动健康检查：确保后端服务中的 Pod 处于可用的状态。在应用服务进行滚动更新时，会牵扯大量的节点进行更新，不健康的节点将会被 APISIX 的负载均衡器忽略，开启健康检查能够有效的挑选出可用的 Pod，从而确保服务的可用性。
* 被动健康检查：相比主动健康检查，被动的方式无需发起额外的探针，若一个健康节点连续 N 个请求都被判定为失败（取决于如何配置），则该节点将被标记为不健康。由于无法提前感知节点的状态，可能会有一定量的失败请求，在滚动更新时这种情况会相对常见（最终节点都会被替换），可以通过服务降级来避免失败的请求量。

> 需要注意的是：由于不健康的节点无法收到请求，仅使用被动健康检查策略无法重新将节点标记为健康。

#### 服务熔断

在微服务架构中，各个微服务之间存在多维的依赖关系，调用链路会串联多个微服务，如果某个服务出现故障，将影响调用链路的可用性。如果在短时间内有大量请求进入该调用链路，这些请求堆积在故障服务的下游服务中，最后可能会导致该调用链路出现雪崩。

### 支持更多的插件

### 支持更多的鉴权方式

* JWT
* HMAC
* wolf-rbac

## 相比 Ingress NGINX，APISIX Ingress 支持哪些扩展方式

在 Ingress NGINX 中，只能通过嵌入 lua 编写的程序的方式来扩展功能，可扩展性比较有限，而 APISIX 具备了更丰富的扩展能力，其扩展方式主要是通过开发自定义 Plugin 完成的。当前主要支持如下几种 Plugin 的开发方式：

* 通过 Lua 进行插件的开发：这种方式相对简单，并且几乎没有性能损耗；
* 通过 *-plugin-runner 开发：这种模式下支持 JAVA/Python/Go 等语言进行开发，这可以方便用户利用一些现有的业务逻辑，并且无需学习新语言；
* 通过 WASM 进行插件插件：这种模式下，可以使用任何支持构建出 WASM 的语言进行插件开发；

此外还可以通过 serverless plugin 来直接书写 Lua 代码，快速的满足业务需求。

当然，如果你有 Lua 模块的开发经验，也可以直接写 Lua 模块，然后进行加载即可，增加如下配置即可：

```yaml
apisix:
    ...
    extra_lua_path: "/path/to/example/?.lua"
```

> 具体的 Plugin 开发步骤和使用，请参考:
[Apache APISIX 的插件开发文档](https://apisix.apache.org/docs/apisix/plugin-develop/)
[APISIX Ingress 如何支持自定义插件](https://api7.ai/blog/how-does-apisix-ingress-support-custom-plugins)。
[APISIX Ingress 如何使用 go-plugin-runner](https://apisix.apache.org/docs/ingress-controller/tutorials/how-to-use-go-plugin-runner-in-apisix-ingress/)

### Lua 扩展，多语言扩展

### Serverless

## 为什么 APISIX Ingress 选择自身 CRD，哪有些好处？

目前 Apache APISIX Ingress Controller 支持两种声明式配置，Ingress Resource 和 CRD Resource。前者比较适合从 Ingress-Nginx 替换过来的网关控件，在转换成本上是最具性价比的。但是它的缺点也比较明显，比如语义化能力太弱、没有特别细致的规范等，同时能力拓展也只能通过 Annotation 去实现，而 Annotations 却无法支撑更复杂的配置。使用 CRD 主要有以下好处：

* 更契合数据面的设计语义，更加简单易用。
* 一些重要配置能够被复用，而不会存在冗余庞大的单个配置。
* 功能性和可扩展能力有了巨大提升（Ingress 只能使用 Annotation 的方式进行扩展）

## Ingress NGXIN 的致命缺点：不支持配置热加载

### 静态配置会带来什么问题？

Ingress NGINX 主要基于 NGINX 配置文件的方式，尽管使用 openresy 平台来进行功能扩展，但没有彻底解决静态配置文件的问题。在路由能力和加载模式上稍显不足，并且存在一些明显劣势。比如添加、修改任何新的规则时，需要重新加载配置才能完成新 NGINX 配置的更新。随着越来越多的路由规则，包括证书变更时，都会引发 reload ，reload 操作将会更耗时，甚至需要几秒到十几秒的时间，对线上流量的影响将会非常大的，会导致流量短暂中断、影响响应延迟、负载平衡质量（每次重新加载 Nginx 都会重置负载平衡状态）等。

### Ingress NGINX 在什么情况下需要重新加载 NGINX

> 值得注意的是：Endpoints 发生变更，NGINX 不会重新加载程序。
在每个端点更改时，Ingress NGINX 会生成相应的后端对象并发送到在 Nginx 中运行的 Lua 处理程序中。Lua 代码依次将这些后端存储在共享内存区域中。然后对于在上下文中运行的每个请求，Lua 代码 balancer_by_lua 检测它应该选择哪些 upstream peer。此功能可以节省大量的 Nginx 重新加载。

* 创建新的 Inresss 资源。
* 将TLS 部分添加到现有 Ingress。
* Ingress Annotations 的变化可能影响上游配置。（例如load-balance注释不需要重新加载）
* 在 Ingress 中添加或删除 path。
* Ingress、Service、Secret 资源被删除。
* Secret 发生更新。

尽管 Ingress NGINX 支持了上游节点的热加载，但是以上这些情况，覆盖到大量的使用情况，在具有频繁部署应用程序的相对较大的集群中，重新加载 NGINX 操作也将变得更加频繁，那将会对生产环境带来很大的影响。

### APISIX Ingress 相比 Ingress NGINX 更符合作为云原生下微服务网关的 Ingress Controller

Apache APISIX 是一个动态、实时、高性能的开源 API 网关，提供负载均衡、动态上游、灰度发布、服务熔断、身份认证、可观测性等丰富的流量管理功能。APISIX Ingress 在架构上分成了两部分，一部分是 APISIX Ingress Controller，作为控制面它将完成配置管理与分发。另一部分 APISIX(代理) 负责承载业务流量。
同时 APISIX Ingress 还具有以下特性：

* 支持高级路由匹配规则以及自定义资源，原生支持 APISIX 多种插件，支持自定义插件扩展；
* 支持 K8s 原生 Ingress 配置；
* 通过 CRD 方式，支持 APISIX 自身路由，全动态，SSL 证书、插件和流量切分功能等；
* 支持 gRPC 与 TCP/UDP， Dubbo 等协议代理；
* 服务自动注册发现，无惧 Pod 扩缩容，支持服务的多种解析粒度（Pod IP, Service IP）；
* 更灵活的负载均衡策略，更完善的流量治理能力；

## 云原生新一代网关标准 Gateway API

### Gateway API 规范有什么优势，为什么许多 Ingress Controller 都选择支持它

Gateway API 相比 Ingress 的功能性更强，旨在通过由许多供应商实现并具有广泛行业支持的富有表现力、可扩展和面向角色的接口来发展 Kubernetes 服务网络。Gateway API 具有如下的特性：

* 面向角色：Gateway 是由一组 API 资源组成的。不同的 API 资源代表了使用与配置 Kubernetes 网络资源的不同角色。

* 表现力强：Gateway API 的核心功能就包含诸如基于头的匹配、流量加权以及其他在 Ingress 中只能通过各实现者自定义的非标准化 annotations 等方式实现的功能。

* 可扩展：Gateway API 允许不同资源在不同层级一同使用。这使得能够对 API 结构进行更精细化的控制。

此外，该标准还包含了可移植性、共享网关与跨命名空间引用等功能。

![Gateway API](https://camo.githubusercontent.com/d50e4a7396242f8200c4ef83dda9b5b366e2aa3f60783188147988a453bfa831/68747470733a2f2f676174657761792d6170692e736967732e6b38732e696f2f696d616765732f6170692d6d6f64656c2e706e67)

#### 目前支持情况

Gateway API 作为一种扩展 Kuberntes 服务网络的标准，能力和表现相比 Ingress 更为出色，其 Gateway 资源能够实现作为 Kubernetes API 来管理网关的生命周期，许多 Ingress Controller 都会选择支持它。而 Ingress NGXIN 目前没有跟进 Gateway API 的计划，在 APISIX Ingress 中，目前实现的处于 Alpha 阶段，已经支持了大部分的特性：

* HTTPRoute
* TCPRoute
* TLSRoute
* UDPRoute

[APISIX Ingress 使用 Gateway API](https://apisix.apache.org/zh/docs/ingress-controller/aeps/gateway-api/)
[APISIX 支持情况](https://github.com/apache/apisix-ingress-controller/issues/644)

## 总结

同为 NGINX 技术系列，Ingress NGINX 在一些大集群中使用时会存在流量中断的问题，无论是其内置大量的插件功能，包括可扩展性、动态路由能力等等，各方面特性 APISIX Ingress 都优于 Ingress NGINX，显然，在复杂场景和大量规则的大规模集群场景下，APISIX Ingress 具备很大的优势。

## 引用

[为什么选择 APISIX Ingress](https://www.apiseven.com/usercase/youpai-cloud)
