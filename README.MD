Running on Java 16

```mvn compile``` or ```docker build -t mavenexample -f DockerfileJava16 .``` gives
```
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.8.1:compile (default-compile) on project broken: Fatal error compiling: java.lang.IllegalAccessError: class lombok.javac.apt.LombokProcessor (in unnamed module @0x21bd20ee) cannot access class com.sun.tools.javac.processing.JavacProcessingEnvironment (in module jdk.compiler) because module jdk.compiler does not export com.sun.tools.javac.processing to unnamed module @0x21bd20ee -> [Help 1]
```

```mvn compile -Ptoolchain``` or ```docker build -t mavenexample -f DockerfileJava16Toolchain .``` gives
```
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.8.1:compile (default-compile) on project broken: Compilation failure -> [Help 1]
```

Is it possible to get the same error information when using the toolchain?

My usecase is having a quick way to build the same code with 2 different versions of Java. To show one version works and the other fails. It's also possible with Docker or setting the JAVA_HOME variable. But I was curious to see if it would work with toolchains as well.
