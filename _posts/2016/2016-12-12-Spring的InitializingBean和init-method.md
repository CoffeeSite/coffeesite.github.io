---
layout: post
category : linux
tagline: "Think More"
tags : [linux, shell]
---
{% include JB/setup %}


Spring在配置完bean以后，会检查bean是否实现了InitializingBean接口，如果实现就调用bean的afterPropertiesSet方法。另外,如果bean是单例的,则afterPropertiesSet方法只会被调用一次;否则每次创建bean时afterPropertiesSet方法都会被重新调用.
同时Spring也可以通过配置init-method来实现加载配置后来方法调用，如果bean实现了InitializingBean接口，则会先调用bean的afterPropertiesSet方法。在调用bean的init-method方法。需要注意的是init-method中定义的方法不能够有参数。