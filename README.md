# SCBP （springcloud boilerplate）
# 项目组成元素
1. 服务注册发现（Eureka）
2. 断路器（Hystrix）
3. 智能路由（Zuul)
4. 客户端负载均衡（Ribbon）
5. 持续集成
# 项目架构图
![](https://github.com/halower/SCBP/blob/master/images/scbp.png)
# 项目解决方案
scbp.eureka-server: 服务注册和发现     
scbp.eureka-{服务名}-client: 服务提供者     
scbp.config-server-git: 配置中心        
# 使用说明
## 如何获取配置信息
1. 引入以下依赖
```
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-config</artifactId>
</dependency>
```
2. 创建bootstrap.yml配置,指定从配置中心获取相关的配置信息
```
spring:
  application:
    name: your application' name
  cloud:
    config:
      uri: http://localhost: 9003
      profile: default
      label: master

server:
  port: your port
```
3. 现在即可直接通过当前应用访问到所需配置，etc. http://localhost:9005/name

