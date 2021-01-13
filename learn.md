# java

https://docs.microsoft.com/en-us/learn/paths/java-on-azure/

mvn archetype:generate \
  -DgroupId=com.microsoft.example \
  -DartifactId=MyWebApp \
  -DarchetypeArtifactId=maven-archetype-webapp \
  -DinteractiveMode=false

<project xmlns="http://maven.apache.org/POM/4.0.0"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.microsoft.example</groupId>
  <artifactId>MyWebApp</artifactId>
  <packaging>war</packaging>
  <version>1.0-SNAPSHOT</version>
  <name>MyWebApp Maven Webapp</name>
  <url>http://maven.apache.org</url>
  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>3.8.1</version>
      <scope>test</scope>
    </dependency>
  </dependencies>
  <build>
    <finalName>MyWebApp</finalName>
    <plugins>
      <plugin>
        <groupId>org.apache.tomcat.maven</groupId>
        <artifactId>tomcat7-maven-plugin</artifactId>
        <version>2.2</version>
      </plugin>
    </plugins>  
  </build>
</project>

mvn tomcat7:run

<plugin>
  <groupId>com.microsoft.azure</groupId>
  <artifactId>azure-webapp-maven-plugin</artifactId>
  <version>1.9.0</version>
</plugin>

mvn azure-webapp:config

mvn clean package

mvn package azure-webapp:deploy