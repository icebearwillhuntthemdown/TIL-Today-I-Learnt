# Spring Boot 2
Spring Boot is a framework that helps developers build stand-alone, production-grade, Spring-based applications that they can run easily and quickly. With Spring Boot 2, we don't have to write the same configuration over and over again, as almost everything is auto-configured.

## Features
* **Spring Boot Starters**
  Spring Boot starters are modules to quickly help you get started with commonly used technologies like Spring MVC, JPA, etc. 
* **Auto-Configuration**
  Spring Boote configures many components automatically, so that we don't need to manually set up boilerplate configuration. For example, if you have the spring-webmvc dependency, Spring Boot assumes you are building a Spring MVC application, and automatically registers DispatcherServlet.
* **Embedded Servlet Container**
  Usually with web applications, you have to create a WAR file and deploy it to an external WAS like Tomcat. However, with Spring Boot you can just create a self-contained Jar application with an embedded servlet container.

