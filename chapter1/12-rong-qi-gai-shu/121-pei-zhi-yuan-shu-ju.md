# 1.2.1 配置元数据

如上图所示，Spring IOC使用某种配置元数据的方法，作为开发人员，您需要在配置元数据中告诉Spring在应用程序中如何实例化、配置、和组装对象。

传统上，配置元数据以简单直观的XML格式提供，在本章中，大部分内容也是以XML的形式来传达Spring容器的关键概念和功能。

> XML并不是配置元数据的唯一方式，Spring IOC容器本身完全与使用哪一种配置元数据方式分离。目前，很多开发人员使用基于[Java的配置](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#beans-java)编写他们的Spring应用程序。

有关在Spring IOC容器中使用其他方式配置元数据的信息，请参阅：

- [基于注解配置](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#beans-annotation-config) : Spring2.5引入了对基于注解配置的支持。
- [基于Java配置](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#beans-java): 从3.0开始, 许多由Java配置的功能都成为了Spring FrameWork的一部分。因此，您可以在应用程序外部使用Java而非XML来定义bean。要使用这些新功能，请参阅`@Configuration`，`@Bean`，`@Import`，`@DependsOn`注解。

Spring配置是容器必须管理的一个或者多个bean定义构成的。在基于XML配置的元数据中，这些bean被定义在`<bean>`，顶级元素为`<beans/>`。Java配置通常在`@Configuration`类中使用`@Bean`注解的方法。

这些bean定义相当于应用程序中的那些实际的对象。通常您定义服务层对象，数据访问对象（DAOs），表示对象（例如Structs的`Action`实例），基础设施对象例如Hibernate的 `SessionFactories`, JMS的 `Queues`等。通常在容器中不会配置细粒度域对象，因为通常是由DAO和业务逻辑负责创建和加载域对象。然而，您可以使用Spring与AspectJ的集成/来配置/在IOC容器控制之外创建的/对象。参阅 [使用Aspectj与Spring依赖注入域对象](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#aop-atconfigurable)查看更多信息。

以下实例展示了基于XML配置的元数据的基本结构：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="..." class="...">
        <!-- 该bean的协作对象和定义在这里编写 -->
    </bean>

    <bean id="..." class="...">
        <!-- 该bean的协作对象和定义在这里编写 -->
    </bean>

    <!-- 更多bean的定义 -->

</beans>
```

 `id` 属性是一个字符串，用于识别单个bean的定义。 `class` 属性定义了bean的类型，并且为全限定类型。id属性值引用协作对象。本例没有展示如何引用协作对象 。详情参见[依赖关系](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#beans-dependencies)。

