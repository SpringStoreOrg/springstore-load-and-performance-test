[![CircleCI](https://circleci.com/gh/SpringStoreOrg/springstore-load-and-performance-test.svg?style=shield)](https://app.circleci.com/pipelines/github/SpringStoreOrg/springstore-load-and-performance-test?branch=main) [![Maven](https://badgen.net/badge/icon/maven?icon=maven&label)](https://https://maven.apache.org/)
[![Open Source? Yes!](https://badgen.net/badge/Open%20Source%20%3F/Yes%21/blue?icon=github)](https://github.com/Naereen/badges/)

# Spring Store - JMeter Load Testing Project  

## Getting Started

[Download JMeter from Apache](http://jmeter.apache.org/download_jmeter.cgi)

Fork source code to local machine. Open file [getProducts.jmx](src/test/jmeter/getProducts.jmx) for more detail about test scenario.

![JMeter application](https://thumbs2.imgbox.com/fc/3c/jptfcCyr_t.png)

### Installing

Run command to run JMeter by maven plugin
```
mvn verify
```

## Built With

* [Maven](https://maven.apache.org/) - Dependency Management
* JMeter Plug-in

```
<plugins>
  <plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-surefire-plugin</artifactId>
    <version>2.14.1</version>
  </plugin>
  <plugin>
    <groupId>com.lazerycode.jmeter</groupId>
    <artifactId>jmeter-maven-plugin</artifactId>
    <version>2.2.0</version>
    <executions>
      <execution>
        <id>jmeter-tests</id>
        <phase>verify</phase>
        <goals>
          <goal>jmeter</goal>
        </goals>
      </execution>
    </executions>
  </plugin>
  <plugin>
    <groupId>com.lazerycode.jmeter</groupId>
    <artifactId>jmeter-analysis-maven-plugin</artifactId>
    <version>1.0.6</version>
    <executions>
      <execution>
        <phase>verify</phase>
        <goals>
          <goal>analyze</goal>
        </goals>
        <configuration>
          <source>${project.build.directory}/**/*.jtl</source>
          <targetDirectory>${project.build.directory}/jmeter/results</targetDirectory>
          <processAllFilesFound>true</processAllFilesFound>
        </configuration>
      </execution>
     </executions>
  </plugin>
</plugins>
```

