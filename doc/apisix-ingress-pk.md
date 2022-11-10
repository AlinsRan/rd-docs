---
title: "为什么 APISIX Ingress 是比 Ingress NGINX 更好的选择？"
description: "对比 APISIX Ingress 和 Ingress NGINX 之间有什么区别"
slug: "/blog/apisix-ingress-vs-ingress-nginx-2"
category: Technology & Products
site:
  - "api7.ai"
tags:
  - "Apache APISIX"
  - "Ingress"
  - "Kubernetes"
keywords:
  - "Apache APISIX"
  - "Ingress"
  - "Kubernetes"
published_at: 2022-11-09T14:38:00.000Z
author_name: ""
author_avatar_url: ""
author_bio: ""
canonical_url: ""
cover_url: ""
---

Ingress NGINX 是 Kubernetes 社区实现的 Ingress Controller，在社区中被广泛使用。那么 Ingress NGINX 有着什么样的痛点呢，APISIX Ingress 解决了 Ingress NGINX 的哪些问题？APISIX Ingress 具备了哪些能力？为什么说 APISIX Ingress 是比 Ingress NGINX 更好的选择？本文通过对比两个 Ingress Controller 实现之间的差异性来回答这些问题，从而帮助你进行 Ingress Controller 选型。

## APISIX Ingress vs Ingress Nginx

> 数据取自：<https://docs.google.com/spreadsheets/d/191WWNpjJ2za6-nbG4ZoUMXMpUK8KlCIosvQB0f-oq3k/edit?ts=5fd6c769#gid=907731238>

### 功能对比

|Product/Project| | |Ingress Nginx |Apache APISIX|
|:----|:----|:----|:----|:----|
|1. General info| | | | |
| |Based on| |nginx|nginx|
| |Documentation| |https://kubernetes.github.io/ingress-nginx/|https://github.com/apache/apisix-ingress-controller/blob/master/README.md|
|2. Protocols| | | | |
| |HTTP/HTTPS| |✔️|✔️|
| |HTTP2| |✔️|✔️|
| |gRPC| |✔️|✔️|
| |TCP| |Partial|✔️|
| |TCP+TLS| |✖︎|✔️|
| |UDP| |Partial|✔️|
| |Websockets| |✔️|✔️|
| |Proxy Protocol| |✔️|✔️|
| |QUIC/HTTP3| |Preview|Preview|
|3. Clients| | | | |
| |Rate limiting (L4)| |✔️|Needs help|
| |Rate limiting (L7)| |✔️|✔️|
| |WAF| |✔️|Partial|
| |Timeouts| |✔️|✔️|
| |Safe-list/Block-list| |✔️|✔️|
| |Authentication| |✔️|✔️|
| |Authorisation| |✖︎|✔️|
|4. Traffic routing| | | | |
| |Host| |✔️|✔️|
| |Path| |✔️|✔️|
| |Headers| |✔️|✔️|
| |Querystring| |✔️|✔️|
| |Method| |✔️|✔️|
| |ClientIP| |✔️|✔️|
| |Notes| | | |
| | | |Notes|Notes|
|5. Upstream probes/resiliency| | | | |
| |Healthchecks| |✖︎|✔️|
| |Retries| |✔️|✔️|
| |Circuit Breaker| |✖︎|✔️|
|6.Load balancer strategies| | | | |
| |Round robin| |✔️|✔️|
| |Sticky sessions| |✔️|✔️|
| |Least connections| |✖︎|✔️|
| |Ring hash| |✔️|✔️|
| |Maglev| |✖︎|✖︎|
| |Exponential-Weighted-Moving-Average| |✔️|✔️|
| |Custom load balancing| |✖︎|✔️|
| |Power of two random choices| |Needs help|Needs help|
| |Global load balancing| |Needs help|✔️|
| |External load balancing| |Needs help|Needs help|
| |Notes| | | |
| | | |Notes|Notes|
|7. Authentication| | | | |
| |Basic auth| |✔️|✔️|
| |External Auth| |✔️|✔️|
| |Client certificate - mTLS| |✔️|✔️|
| |OAuth| |✔️|✔️|
| |OpenID| |✖︎|✔️|
| |JWT| |✖︎|✔️|
| |LDAP| |✖︎|✔️|
| |HMAC| |✖︎|✔️|
| |SAML| |Needs help|✔️|
|8. Observability| | | | |
| |Logging| |✔️|✔️|
| |Metrics| |✔️|✔️|
| |Tracing| |✔️|✔️|
|9. Kubernetes Integration| | | | |
| |State| |Kubernetes|Kubernetes|
| |CRD| |✖︎|✔️|
| |Scope| |Clusterwide and namespace|namespace|
| |Support for the Gateway API| |✖︎|Preview|
| |Integrates with service meshes| |✔️|✔️|
|10. Traffic shaping| | | | |
| |Canary| |✔️|✔️|
| |Session Affinity| |✔️|✔️|
| |Traffic Mirroring| |✔️|✔️|
|11. Interface| | | | |
| |Dashboard| |✖︎|✔️|
| |Billing and reporting| |✖︎|✔️|
| |Developer portal| |✖︎|✔️|
|12. Other| | | | |
| |Hot reloading| |✔️|✔️|
| |LetsEncrypt Integration| |✔️|✔️|
| |Transparent update of certificates| |Needs help|✔️|
| |Wildcard certificate support| |✔️|✔️|
| |Configure hot reloading| |Preview|✔️|
| |Service Discovery | |✖|✔️|

功能很多，总体来说，Ingresss NGINX 支持的功能，APISIX Ingress 基本都支持，但反过来，却未必一定，为了方便阅读，将截取它们之间一些更重要的功能来进行对比。

### 差异

![背景](https://raw.githubusercontent.com/AlinsRan/rd-docs/main/images/apisix-ingress-vs-ingress-nginx.jpg)

通过上图，可以粗略看到 APISIX Ingress 内置的功能和特性相比 Ingress NGINX 更加丰富，其中包括协议支持，认证鉴权，服务发现等等，接下来将具体介绍它们之间的差异，以及 Inress NGINX 的静态配置将会带来哪些问题。

## APISIX Ingress 支持更多的内置基本能力

### 更多协议支持和服务发现

当业务量发生变化时，需要对应用服务进行扩缩容，面对这些不断变化的应用服务节点，如果网关是通过配置来维护上游服务信息，在微服务架构模式下，自行维护成本就很高了。在 APISIX 中，能够通过网关层面来支持服务发现，实时动态的感知到上游服务节点的变化，目前已支持以下服务发现：

* [DNS](https://apisix.apache.org/docs/apisix/next/discovery/dns/)
* [nacos](https://apisix.apache.org/docs/apisix/next/discovery/nacos/)
* [eureka](https://apisix.apache.org/docs/apisix/next/discovery/eureka/)
* [consul_kv](https://apisix.apache.org/docs/apisix/next/discovery/consul_kv/)

APISIX 在协议支持上也十分丰富，能够使用 TLS 来加密 TCP 流量，还支持 [MQTT](https://apisix.apache.org/docs/apisix/next/plugins/mqtt-proxy/)，[Dubbo](https://apisix.apache.org/docs/apisix/next/plugins/dubbo-proxy/)、[kafka](https://apisix.apache.org/docs/apisix/next/plugins/kafka-proxy/) 等协议进行代理。

### 完善的服务治理能力

#### 健康检查

APISIX Ingress 支持健康检查（主动和被动），通过探针的形式探测 Pod 的可用性，从而减少或避免流量损失。

* 主动健康检查：确保后端服务中的 Pod 处于可用的状态。在应用服务进行滚动更新时，会牵扯大量的节点进行更新，不健康的节点将会被 APISIX 的负载均衡器忽略，开启健康检查能够有效的挑选出可用的 Pod，从而确保服务的可用性。
* 被动健康检查：相比主动健康检查，被动的方式无需发起额外的探针，若一个健康节点连续 N 个请求都被判定为失败（取决于如何配置），则该节点将被标记为不健康。由于无法提前感知节点的状态，可能会有一定量的失败请求，在滚动更新时这种情况会相对常见（最终节点都会被替换），可以通过服务降级来避免失败的请求量。

> 需要注意的是：由于不健康的节点无法收到请求，仅使用被动健康检查策略无法重新将节点标记为健康。

为 httpbin 服务配置健康检查示例：

```yaml
apiVersion: apisix.apache.org/v2
kind: ApisixUpstream
metadata:
  name: httpbin
spec:
  healthCheck:
    passive:
      unhealthy:
        httpCodes:
          - 500
          - 502
          - 503
          - 504
        httpFailures: 3
        timeout: 5s
    active:
      type: http
      httpPath: /healthz
      timeout: 5s
      healthy:
        successes: 3
        interval: 2s
        httpCodes:
          - 200
          - 206

```

#### 服务熔断

网关作为流量的入口，大量请求进入网关，向后端远程系统或服务发起调用，后端服务不可避免的会产生调用失败（超时或者异常），失败时不能让请求堆积在网关上，需要快速失败并返回回去，这就需要在网关上做熔断。在 APISIX 中可以通过 [api-breaker](https://apisix.apache.org/docs/apisix/plugins/api-breaker/) 插件来实现熔断。

配置熔断示例：

```yaml
apiVersion: apisix.apache.org/v2
kind: ApisixRoute
metadata:
 name: httpbin-route
spec:
 http:
 - name: rule1
   match:
     hosts:
     - httpbin.org
     paths:
       - /status/*
   backends:
   - serviceName: httpbin
     servicePort: 80
   plugins:
   - name: api-breaker
     enable: true
     config:
       break_response_code: 502
       unhealthy:
         http_statuses:
         - 505
         failures: 2
       healthy:
         http_statuses:
         - 200
         successes: 2
```

### 支持更多的插件和鉴权方式

Ingress NGINX 主要通过 [Annotations](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/) 等方式进行配置，支持的插件功能比较有限。
APISIX Ingress 原生支持 APISIX 内置的 [80+ 插件](https://github.com/apache/apisix/blob/3.0.0/conf/config-default.yaml#L391-L473)，相比 Ingress NGINX，APISIX Ingress 还支持（JWT、HMAC、wolf-rbac）等更多的鉴权方式。

使用 HMAC 认证并在路由上应用示例：

```yaml

apiVersion: apisix.apache.org/v2
kind: ApisixConsumer
metadata:
  name: hmac-value
spec:
  authParameter:
    hmacAuth:
      value:
        access_key: papa
        secret_key: fatpa
        algorithm: "hmac-sha256"
        clock_skew: 0

---

apiVersion: apisix.apache.org/v2
kind: ApisixRoute
metadata:
 name: httpbin-route
spec:
 http:
 - name: rule1
   match:
     hosts:
     - httpbin.org
     paths:
       - /ip
   backends:
   - serviceName: httpbin
     servicePort: 80
   authentication:
     enable: true
     type: hmacAuth
```

## Ingress NGINX 和 APISIX Ingress 扩展方式有什么不同

### Ingress NGINX 如何进行功能扩展

Ingress NGINX 通过插件来进行扩展，在扩展方式上比较单一，只能通过嵌入 Lua 程序的方式来扩展功能，可扩展性比较有限，需要具备 NGINX + Lua 技术栈。

Ingress NGINX 插件开发示例：
> [自定义 Plugin 开发步骤](https://github.com/kubernetes/ingress-nginx/blob/main/rootfs/etc/nginx/lua/plugins/README.md)

1. 编写 Lua 程序 example-plugin
2. 将插件安装到 ingress-nginx pod 中的 `/etc/nginx/lua/plugins/<your plugin name>` $\rightarrow$ `/etc/nginx/lua/plugins/example-plugin`
3. 在 ConfigMap 中启用 example-plugin 插件，需要在安装 Ingress NGINX 时引用此 ConfigMap 对象。

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: ingress-nginx-controller
  namespace: ingress-nginx
data:
  plugins: "example-plugin"
```

### APISIX Ingress 如何进行功能扩展

APISIX 具备了更丰富的扩展能力，其扩展方式主要是通过开发自定义 Plugin 完成的。当前主要支持如下几种 Plugin 的开发方式：

* 通过 Lua 进行插件的开发：这种方式相对简单，并且几乎没有性能损耗；
* 通过 *-plugin-runner 开发：这种模式下支持 JAVA/Python/Go 等语言进行开发，这可以方便用户利用一些现有的业务逻辑，并且无需学习新语言；
* 通过 WASM 进行插件插件：这种模式下，可以使用任何支持构建出 WASM 的语言进行插件开发；

此外还可以通过 serverless plugin 来直接编写 Lua 代码，快速的满足业务需求。

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

## 为什么 APISIX Ingress 选择维护 CRD

目前 Apache APISIX Ingress Controller 支持三种声明式配置，Ingress Resource 、CRD Resource 和 Gateway API。前者比较适合从 Ingress NGINX 替换过来的网关控件，在转换成本上是最具性价比的。但是它的缺点也比较明显，比如语义化能力太弱、没有特别细致的规范等，同时能力拓展也只能通过 Annotation 或者 configmap 去实现，而 Annotations 却无法支撑更复杂的配置。使用 CRD 主要有以下好处：

* 更契合数据面的设计语义，更加简单易用。
* 一些重要配置能够被复用，而不会存在冗余庞大的单个配置。
* 功能性和可扩展能力有了巨大提升（Ingress 只能使用 Annotation 的方式进行扩展）
* 数据面 APISIX 有着活跃的社区，更新和发布版本快，CRD 的方式能够轻易支持数据面的更多能力。

## Ingress NGXIN 的致命缺点：不支持配置热加载

### 静态配置会带来什么问题？

Ingress NGINX 主要基于 NGINX 配置文件的方式，尽管使用 OpenResty 平台来进行功能扩展，但没有彻底解决静态配置文件的问题。在路由能力和加载模式上稍显不足，并且存在一些明显劣势。比如添加、修改任何新的规则时，需要重新加载配置才能完成新 NGINX 配置的更新。随着越来越多的路由规则，包括证书变更时，都会引发 reload ，reload 操作将会更耗时，甚至需要几秒到十几秒的时间，对线上流量的影响将会非常大的，会导致流量短暂中断、影响响应延迟、负载平衡质量（每次重新加载 Nginx 都会重置负载平衡状态）等。

### Ingress NGINX 在什么情况下需要重新加载 NGINX

> 值得注意的是：Endpoints 发生变更，NGINX 不会重新加载程序。
在每个端点更改时，Ingress NGINX 会生成相应的后端对象并发送到在 Nginx 中运行的 Lua 处理程序中。Lua 代码依次将这些后端存储在共享内存区域中。然后对于在上下文中运行的每个请求，Lua 代码 balancer_by_lua 检测它应该选择哪些 upstream peer。此功能可以节省大量的 Nginx 重新加载。

* 创建新的 Inresss 资源。
* 将TLS 部分添加到现有 Ingress。
* Ingress Annotations 的变化可能影响上游配置。（例如load-balance注释不需要重新加载）
* 在 Ingress 中添加或删除 path。
* Ingress、Service、Secret 资源被删除。
* Secret 发生更新。

尽管 Ingress NGINX 支持了上游节点的热加载，但是以上这些情况，覆盖到大量的使用场景，在具有频繁部署应用程序的相对较大的集群中，重新加载 NGINX 操作也将变得更加频繁，那将会对生产环境带来很大的影响。

### 小结

NGINX 静态配置带来的问题不可避免，而 APISIX 的诞生彻底解决了这个问题，尽管基于 NGINX 平台，但通过 Lua 定时器及 lua-resty-etcd 模块实现了配置的动态管理，由 etcd watch 机制来实现配置同步，Apache APISIX 作为一个动态、实时、高性能的开源 API 网关，得意于活跃的社区和许多贡献者，使得 APISIX 具备了丰富的功能，包括负载均衡、动态上游、灰度发布、服务熔断、身份认证、可观测性等能力。

APISIX Ingress 基于 APISIX 作为控制面与 Kuberntes 进行集成，在架构上分成了两部分，一部分是 APISIX Ingress Controller，作为控制面它主要负责配置管理与分发。另一部分 APISIX(数据面) 负责承载业务流量。

![APISIX Ingress 架构图](https://raw.githubusercontent.com/apache/apisix-ingress-controller/master/docs/assets/images/module-0.png)

APISIX Ingress 还具有以下特性：

* 支持高级路由匹配规则以及自定义资源，原生支持 APISIX 多种插件，支持自定义插件扩展；
* 支持 K8s 原生 Ingress 配置；
* 通过 CRD 方式，支持 APISIX 自身路由，全动态，SSL 证书、插件和流量切分功能等；
* 支持 gRPC 与 TCP/UDP，Dubbo 等协议代理；
* 服务自动注册发现，无惧 Pod 扩缩容，支持服务的多种解析粒度（Pod IP, Service IP）；
* 更灵活的负载均衡策略，更完善的流量治理能力；

## 云原生新一代网关标准 Gateway API

### Gateway API 规范有什么优势，为什么许多 Ingress Controller 都选择支持它

Gateway API 相比 Ingress 的功能性更强，旨在通过由许多供应商实现并具有广泛行业支持的富有表现力、可扩展和面向角色的接口来发展 Kubernetes 服务网络。Gateway API 具有如下的特性：

* 面向角色：Gateway 是由一组 API 资源组成的。不同的 API 资源代表了使用与配置 Kubernetes 网络资源的不同角色。

* 表现力强：Gateway API 的核心功能就包含诸如基于头的匹配、流量加权以及其他在 Ingress 中只能通过各实现者自定义的非标准化 Annotations 等方式实现的功能。

* 可扩展：Gateway API 允许不同资源在不同层级一同使用。这使得能够对 API 结构进行更精细化的控制。

此外，该标准还包含了可移植性、共享网关与跨命名空间引用等功能。

![Gateway API](https://camo.githubusercontent.com/d50e4a7396242f8200c4ef83dda9b5b366e2aa3f60783188147988a453bfa831/68747470733a2f2f676174657761792d6170692e736967732e6b38732e696f2f696d616765732f6170692d6d6f64656c2e706e67)

#### 目前支持情况

Gateway API 作为一种扩展 Kuberntes 服务网络的标准，能力和表现相比 Ingress 更为出色，其 Gateway 资源能够实现作为 Kubernetes API 来管理网关的生命周期，许多 Ingress Controller 都在积极支持它。很遗憾的是，**Ingress NGXIN 目前尚未支持 Gateway API**，在 APISIX Ingress 中，已经支持了 Gateway API 的大部分特性：

* HTTPRoute
* TCPRoute
* TLSRoute
* UDPRoute

> 如果你想要了解和体验 Gateway API 特性，那么可以参考:
[APISIX Ingress 使用 Gateway API](https://apisix.apache.org/zh/docs/ingress-controller/aeps/gateway-api/)
[APISIX Ingress 中 Gateway API 的支持情况](https://github.com/apache/apisix-ingress-controller/issues/644)

## 总结

* 更多内置能力：APISIX Ingress 的插件能力上更加灵活，支持更多的鉴权方式，完善的服务治理能力，以及能够对接更多的注册中心等等，在功能性上，Ingress NGINX 是比较差的。
* 静态配置：由于 Ingress NGINX 使用静态配置，随着业务规模的增长，API 数量越来越多，引发流量中断的代价也将越来越高，使用 APISIX Ingress 这个问题将不会存在。
* 可扩展性：如果你有更多定制化网关层面的需求，Ingress NGINX 的扩展方式单一，如果你的技术栈是 NGINX + lua，为什么不选择可扩展性强且能力更丰富的 APISIX？如（Lua、多语言 plugin-runner、serverless、WASM）等多种扩展方式中总有一个合适你。
* 先进性
  * Gateway API：Ingress 表现能力比较有限，只能通过 Annotations 的方式进行扩展，而 Gateway API 作为一种标准规范，极大扩展了 Kubernetes 服务网络的能力，作为 Ingress 功能上的父集，未来几年的时间里会逐步取代 Ingress。
  * 数据面 APISIX 有着极为活跃的社区，不断发布新的功能，使用符合数据面设计语义的 CRD，使 APISIX Ingress 能够轻易的支持新功能。
