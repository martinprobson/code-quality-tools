# Checkstyle 

## CheckStyle
This [plugin](https://maven.apache.org/plugins/maven-checkstyle-plugin/index.html) checks Java code formatting against conventions. 
In this case the plugin has been configured to check against modified [Google's coding conventions](https://google.github.io/styleguide/javaguide.html). 

```xml
<configuration>
    <configLocation>checkstye-checks.xml</configLocation>   <!-- Use modified google code checks -->
    <includeTestSourceDirectory>true</includeTestSourceDirectory> <!-- Include test sources -->
    <suppressionsLocation>checkstyle-suppressions.xml</suppressionsLocation>
    <suppressionsFileExpression>checkstyle.suppressions.file</suppressionsFileExpression>
    <encoding>UTF-8</encoding>
    <consoleOutput>true</consoleOutput>
    <violationSeverity>warning</violationSeverity>          <!-- Flag all warnings as errors build will fail any violations -->
    <failsOnError>true</failsOnError>
    <linkXRef>false</linkXRef>
</configuration>
```

Reload the maven config in IntelliJ and run `mvn checkstyle:check`

There is an [IntelliJ plugin](https://plugins.jetbrains.com/plugin/1065-checkstyle-idea) you can install, 
that can check your code in the same way within IntelliJ itself


## SpotBugs
[Spotbugs](https://spotbugs.github.io/) checks Java bytecode for common bugs. 

```xml
<groupId>com.github.spotbugs</groupId>
<artifactId>spotbugs-maven-plugin</artifactId>
<version>4.1.3</version>
<configuration>
    <effort>Max</effort>
    <threshold>Low</threshold>
    <failOnError>true</failOnError>
    <includeTests>false</includeTests> <!-- Change to True to pick up test classes -->
</configuration>
```

You can use `spotbugs:gui` to review the bugs that have been found.

There is an [IntelliJ Plugin](https://plugins.jetbrains.com/plugin/14014-spotbugs) for spot bugs as well so that the issues can be viewed in the IDE

## Reference

[check style](https://checkstyle.sourceforge.io/)

[Spot bugs](https://spotbugs.github.io/spotbugs-maven-plugin/)

[Setup checkstyle in IntelliJ](https://www.seas.upenn.edu/~cis121/current/resources/guides/style-checker-setup-intellij.html)

