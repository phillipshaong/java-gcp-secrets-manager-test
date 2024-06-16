# GCP Secrets Manager Test for Java


I would like to use GCP Secrets Manager for my Java 9+ application. The main trouble comes when using the module-info.java file, if I use a version of Java less than 9 that doesn't have the module-info.java file, then it works fine. The main error that comes up is `The import com.google.cloud.secretmanager.v1.AccessSecretVersionResponse cannot be resolvedJava(268435846).` However, I am able to use VS Code's intellisense and click into the Class file that the import references.

![image](https://github.com/phillipshaong/java-gcp-secrets-manager-test/assets/64993172/11187dc0-b8b3-49b8-9a2b-13a268539684)

![image](https://github.com/phillipshaong/java-gcp-secrets-manager-test/assets/64993172/1b10b94e-3244-495d-bc5d-5ee23f352761)

Steps to reproduce:

1. Create a new MVN project mvn archetype:generate in a new folder, following prompts.
2. Add the following code in pom.xml in their respective areas to turn it into a Java Version 11 project
```
<properties>
    <java.version>11</java.version>
  </properties>
```
```
<plugin>
          <artifactId>maven-compiler-plugin</artifactId>
          <version>3.8.0</version>
          <configuration>
            <source>11</source>  <!-- same as <java.version> -->
            <target>11</target>    <!-- same as <java.version> -->
          </configuration>
        </plugin>
```
3. Copy and paste quickstart instructions from https://cloud.google.com/secret-manager/docs/reference/libraries#client-libraries-install-java in the main Java file.
