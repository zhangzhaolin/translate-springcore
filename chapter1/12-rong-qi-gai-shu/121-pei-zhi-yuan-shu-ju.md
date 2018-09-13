# 1.2.1 配置元数据

如上图所示，Spring IOC使用某种配置元数据的方法，作为开发人员，您需要在配置元数据中告诉Spring在应用程序中如何实例化、配置、和组装对象。

传统上，配置元数据以简单直观的XML格式提供，在本章中，大部分内容也是以XML的形式来传达Spring容器的关键概念和功能。

> XML并不是配置元数据的唯一方式，Spring IOC容器本身完全与使用哪一种配置元数据方式分离。目前，很多开发人员使用基于[Java的配置](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#beans-java)编写他们的Spring应用程序。

有关在Spring IOC容器中使用其他方式配置元数据的信息，请参阅：

- [基于注解配置](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#beans-annotation-config) : Spring2.5引入了对基于注解配置的支持
- [基于Java配置](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#beans-java): 从3.0开始, 许多由Java配置的功能都成为了Spring FrameWork的一部分。因此，您可以在应用程序外部使用Java而非XML来定义bean。要使用这些新功能，请参阅`@Configuration`，`@Bean`，`@Import`，`@DependsOn`注解。

Spring configuration consists of at least one and typically more than one bean definition that the container must manage. XML-based configuration metadata shows these beans configured as `<bean/>` elements inside a top-level `<beans/>` element. Java configuration typically uses `@Bean` annotated methods within a `@Configuration` class.

These bean definitions correspond to the actual objects that make up your application. Typically you define service layer objects, data access objects (DAOs), presentation objects such as Struts `Action` instances, infrastructure objects such as Hibernate `SessionFactories`, JMS `Queues`, and so forth. Typically one does not configure fine-grained domain objects in the container, because it is usually the responsibility of DAOs and business logic to create and load domain objects. However, you can use Spring’s integration with AspectJ to configure objects that have been created outside the control of an IoC container. See [Using AspectJ to dependency-inject domain objects with Spring](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#aop-atconfigurable).

The following example shows the basic structure of XML-based configuration metadata:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="..." class="...">
        <!-- collaborators and configuration for this bean go here -->
    </bean>

    <bean id="..." class="...">
        <!-- collaborators and configuration for this bean go here -->
    </bean>

    <!-- more bean definitions go here -->

</beans>
```

The `id` attribute is a string that you use to identify the individual bean definition. The `class` attribute defines the type of the bean and uses the fully qualified classname. The value of the id attribute refers to collaborating objects. The XML for referring to collaborating objects is not shown in this example; see [Dependencies](https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#beans-dependencies) for more information.

