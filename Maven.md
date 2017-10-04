# Dependency Hierarchy(Eclipse pom xml view)


Omitted for conflict with <JAR_VERSION>
---------------------------------------

If the same dependency jar is begin referred more than once, then the jar download preference depends on the shortest depth at which the jar is in the Dependency tree.

**Note:** 
If two dependency versions are at the same depth in the dependency tree, until Maven 2.0.8 it was not defined which one would win, but since Maven 2.0.9 it's the order in the declaration that counts: the first declaration wins.

**Refer:**
http://maven.apache.org/plugins/maven-dependency-plugin/examples/resolving-conflicts-using-the-dependency-tree.html

[Provided]
----------

It means that dependency is explicitly linked with the Project. Ex:Adding external dependencies to project.

This is much like compile, but indicates you expect the JDK or a container to provide the dependency at runtime. For example, when building a web application for the Java Enterprise Edition, you would set the dependency on the Servlet API and related Java EE APIs to scope provided because the web container provides those classes. This scope is only available on the compilation and test classpath, and is not transitive.

[test]
------
This scope indicates that the dependency is not required for normal use of the application, and is only available for the test compilation and execution phases.

[Compile]
---------
This is the default scope, used if none is specified. Compile dependencies are available in all classpaths of a project. Furthermore, those dependencies are propagated to dependent projects.

**Refer**
https://stackoverflow.com/questions/26975818/what-is-scope-under-dependency-in-pom-xml-for
