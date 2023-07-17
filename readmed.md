Usando o plugin da google para poder gerar dockerizar a api sem utilizar dockerfile



```
<properties>
		<java.version>11</java.version>
		<spring-boot-admin.version>2.7.4</spring-boot-admin.version>
		<jib-maven-plugin.version>2.8.0</jib-maven-plugin.version>
		<docker.distroless.image>gcr.io/distroless/java:11</docker.distroless.image>
		<docker.repo.url>registry.hub.docker.com/diegorj9315</docker.repo.url>
		<docker.repo.project>spring-admin</docker.repo.project>
		<docker.image.name>${docker.repo.url}/${docker.repo.project}</docker.image.name>
</properties>
```


```
<plugin>
  	<groupId>com.google.cloud.tools</groupId>
  	<artifactId>jib-maven-plugin</artifactId>
  	<version>${jib-maven-plugin.version}</version>
  	<configuration>
    	<from>
      		<image>${docker.distroless.image}</image>
    	</from>
    	<to>
    		<image>${docker.image.name}</image>
    	<tags>
    		<tag>${project.version}</tag>
    	</tags>
    	</to>
   		<mainClass>com.example.demo.SpringAdminApplication</mainClass>		
	</configuration>
</plugin>
```

**Comando para executar o Docker usando o plugin jib sem fazer upload direto para o Docker hub:**

**"mvn jib:dockerBuild"**