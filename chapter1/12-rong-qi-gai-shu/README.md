# 1.2 Spring容器概述

接口 `org.springframework.context.ApplicationContext` 代表Spring IOC容器，负责实例化、配置、组装上述bean。容器通过读取配置数据，来知道哪些对象被实例化、配置、组装。配置源数据可以用XML、Java注解或者Java代码来表示。配置元数据允许您描述组成您应用的对象，以及对象之间丰富的相互依赖性。

`ApplicationContext` 的几个实现类是Spring提供的。在独立应用程序中，通常会创建 [`ClassPathXmlApplicationContext`](https://docs.spring.io/spring-framework/docs/5.0.9.RELEASE/javadoc-api/org/springframework/context/support/ClassPathXmlApplicationContext.html) 或 [`FileSystemXmlApplicationContext`](https://docs.spring.io/spring-framework/docs/5.0.9.RELEASE/javadoc-api/org/springframework/context/support/FileSystemXmlApplicationContext.html)的实例。虽然XML是定义配置元数据的传统格式，但是您还可以通过提供少量XML来配置额外的元数据格式，让容器使用Java注解或者代码的方式作为元数据格式。

在大多数应用程序方案中，用户不需要显示的编写代码来实例化Spring IOC容器的一个或者多个实例。例如，在Web应用程序中，通常web.xml文件编写八行左右的样板代码就足够了（详情参阅[Web应用程序便捷的`ApplicationContext`实例化](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#context-create)）。如果您使用的是基于Eclipse开发的[Spring Tool Suite](https://spring.io/tools/sts)应用程序，通过点点鼠标或者按键就可以创建这些样板式配置文件了。

下面的图片展示了Spring是如何工作的，您的应用程序类和配置元数据结合，以便在`ApplicationContext`创建和初始化之后，您拥有一套完全可配、可运行的系统或应用程序。

![1.Spring IOC&#x5BB9;&#x5668;](http://zhangzhaolin.oss-cn-beijing.aliyuncs.com/18-9-16/71216340.jpg)

