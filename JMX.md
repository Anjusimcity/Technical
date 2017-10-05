JMX - Java Management Extension
-------------------------------
A Java technology that supplies tools for managing and monitoring applications, system objects, devices (such as printers) and service-oriented networks. Those resources are represented by objects called MBeans (for Managed Bean).

It provides an architecture to manage resources dynamically at runtime. JMX is used mostly in enterprise applications to make the system configurable or to get the state of application at any point of time.

We use JMX Connectors to connect to MBean server and to manage the registered resources. For example, JDK comes with JConsole through which you can connect to any local or remote MBean server.

Manageable Resources
--------------------
Different types of resources can be managed using JMX technology, for example an application, an implementation of a service, a device, or a user. For a given resource to be managed by JMX technology, it must be developed in the Java language, or at least offer a Java language wrapper.

Developers of applications and devices can choose the granularity of objects that are instrumented as MBeans. An MBean might represent the smallest object in an application, or it could represent the entire application

https://www.mkyong.com/tomcat/jconsole-jmx-remote-access-on-tomcat/
