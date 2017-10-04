# Dependency Hierarchy(Eclipse pom xml view)


Omitted for conflict with <JAR_VERSION>
---------------------------------------

If the same dependency jar is begin referred more than once, then the jar download preference depends on the shortest depth at which the jar is in the Dependency tree.

**Note:** 
If two dependency versions are at the same depth in the dependency tree, until Maven 2.0.8 it was not defined which one would win, but since Maven 2.0.9 it's the order in the declaration that counts: the first declaration wins.

**Refer:**
http://maven.apache.org/plugins/maven-dependency-plugin/examples/resolving-conflicts-using-the-dependency-tree.html
