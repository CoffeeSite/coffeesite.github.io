---
layout: post
category : linux
tagline: "Think More"
tags : [linux, shell]
---
{% include JB/setup %}



>对于传统的Web项目，为了提升系统的高可用性，我们通常会运用nginx+Tomcat+Redis存储Session来处理。本文旨在提供详细的配置方案来实现Tomcat的集群配置。
##基本环境
- **Redis 2.4.10**
- **Nginx 1.10.1**
- **Tomcat 7**
- **Jdk 7**
-  **Node1 :172.18.50.100**
- **Node2 : 172.18.50.101**

-------------------

## Nginx配置

```
#定义集群的集合,将所有可用的node都添加到upstream中
upstream cluster  
{
    server 172.18.50.100:8080;
    server 172.18.50.191:8080;
}

server {
        listen       80;
        server_name  localhost;
        	
        location /testcluster {
		    proxy_pass    http://cluster;
		}
}
```

##Tomcat配置
> 这里需要修改Tomcat的Session存储机制，将Session交给Redis进行管理。

-  **修改Tomcat的context.xml文件在最后面添加Session的RedisManagement**
```
<Valve className="com.orangefunction.tomcat.redissessions.RedisSessionHandlerValve" />        
    <Manager className="com.orangefunction.tomcat.redissessions.RedisSessionManager" 
        host="172.18.50.100" 
        port="6379" 
        database="0" 
        maxInactiveInterval="60"/>
```
- **给Tomcat添加RedisSessionManagment相应的jar** 
: commons-pool2-2.3.jar
: jedis-2.7.3.jar
: tomcat-redis-session-manager1.2.jar


###至此所有的配置已完成,重启Tomcat实例和Nginx服务,试着访问下你的服务吧.