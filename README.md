# lagom-java-maven-fatjar

How to use it:

```
mvn clean package -DskipTests=true 
java  -Dplay.http.secret.key=a-very-poorly-chosen-secret \
      -Dakka.discovery.method=akka-dns    \
      -jar hello-impl/target/hello-impl-1.0-SNAPSHOT-allinone.jar
```

The steps above will build `hello-impl/target/hello-impl-1.0-SNAPSHOT-allinone.jar` 
and run it in production mode.

NOTE: we're passing two command-line arguments which could be provided as settings on 
`application.conf`.

NOTE 2: the above will not do much because it will not be able to setup 
a cluster. This sample is setup to use a DNS for cluster service 
discovery and running this locally will fail to resolve other nodes.  