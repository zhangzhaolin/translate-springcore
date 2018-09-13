# 1.1 Spring IOC和beans简介

本章介绍了`Spring Framework`实现控制反转\(IOC\)的原理。IOC也被俗称为依赖注入\(DI\)。依赖注入是一个过程，通过依赖注入这个过程，对象定义了与其他对象的依赖关系，这些依赖关系只能通过构造函数参数、工厂函数参数、设置对象实例属性值（对象实例是通过构造函数或者工厂函数返回的）。接着容器在创建bean的时候注入依赖。这个过程基本上是相反的，因此被命名为控制反转（IOC），bean本身通过执行构造类或者通过诸如服务定位模式（Service Locator pattern），来控制其实例化或者位置。

`org.springframework.beans`和`org.springframework.context`两个包是Spring Framework IOC容器最核心的部分。[`BeanFactory`](https://docs.spring.io/spring-framework/docs/5.0.9.RELEASE/javadoc-api/org/springframework/beans/factory/BeanFactory.html)接口提供了一种可以管理任何类型对象的高级配置机制。[`ApplicationContext`](https://docs.spring.io/spring-framework/docs/5.0.9.RELEASE/javadoc-api/org/springframework/context/ApplicationContext.html)类实现了`BeanFactory`. 它提供了与Spring AOP更加方便的集成、消息资源处理（用于国际化）、事件发布以及特定的应用层上下文，例如`WebApplicationContext`应用与web应用程序。

简而言之，`BeanFactory`提供了配置框架和基本功能，`ApplicationContext`提供了更多的企业级特定功能。`ApplicationContext`是`BeanFactory`的完全扩展集，在本章中仅仅用来描述Spring IOC容器。如果您想了解更多关于`BeanFacotry`而不是`ApplicationContext`信息的话，请参阅[`The BeanFactory`](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#beans-beanfactory)。

在Spring中，bean对象是构成应用程序的主干，也被Spring IOC容器所管理。bean是由Spring IOC容器实例化、组装、管理的对象。否则，bean只是应用程序中众多对象之一。beans与其依赖关系反映在被容器使用的配置元数据中。

