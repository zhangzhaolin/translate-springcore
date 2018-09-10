# Spring IOC和beans简介

本章介绍了`Spring Framework`实现控制反转\(IOC\)的原理。IOC也被俗称为依赖注入\(DI\)。依赖注入是一个过程，通过依赖注入这个过程，对象定义了与其他对象的依赖关系，这些依赖关系只能通过构造函数参数、工厂函数参数、设置对象实例属性值（对象实例是通过构造函数或者工厂函数返回的）。接着容器在创建bean的时候注入依赖。这个过程基本上是相反的，因此被命名为控制反转（IOC），bean本身通过执行构造类或者通过诸如服务定位模式（Service Locator pattern），来控制其实例化或者位置。

The`org.springframework.beans`and`org.springframework.context`packages are the basis for Spring Framework’s IoC container. The[`BeanFactory`](https://docs.spring.io/spring-framework/docs/5.0.9.RELEASE/javadoc-api/org/springframework/beans/factory/BeanFactory.html)interface provides an advanced configuration mechanism capable of managing any type of object.[`ApplicationContext`](https://docs.spring.io/spring-framework/docs/5.0.9.RELEASE/javadoc-api/org/springframework/context/ApplicationContext.html)is a sub-interface of`BeanFactory`. It adds easier integration with Spring’s AOP features; message resource handling \(for use in internationalization\), event publication; and application-layer specific contexts such as the`WebApplicationContext`for use in web applications.

In short, the`BeanFactory`provides the configuration framework and basic functionality, and the`ApplicationContext`adds more enterprise-specific functionality. The`ApplicationContext`is a complete superset of the`BeanFactory`, and is used exclusively in this chapter in descriptions of Spring’s IoC container. For more information on using the`BeanFactory`instead of the`ApplicationContext,`refer to[The BeanFactory](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#beans-beanfactory).

In Spring, the objects that form the backbone of your application and that are managed by the Spring IoC_container_are called_beans_. A bean is an object that is instantiated, assembled, and otherwise managed by a Spring IoC container. Otherwise, a bean is simply one of many objects in your application. Beans, and the_dependencies_among them, are reflected in the_configuration metadata_used by a container.

