# sandboxTeam3AOpenApiSchema

This repository stores a .yaml file. In which the specification of the application is stored.
And it generates interfaces based on .yaml file of specification.

## Get started

* **Create** ```settings.xml``` file (if not exist) in ```.m2``` directory and fill by: 
``` 
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
http://maven.apache.org/xsd/settings-1.0.0.xsd">
<activeProfiles>
  <activeProfile>github</activeProfile>
</activeProfiles>

<profiles>
  <profile>
    <id>github</id>
    <repositories>
      <repository>
        <id>central</id>
        <url>https://repo1.maven.org/maven2</url>
      </repository>
      <repository>
        <id>github</id>
        <url>https://maven.pkg.github.com/try-to-laugh/sandboxOpenApiSchema</url>
        <snapshots>
          <enabled>true</enabled>
        </snapshots>
      </repository>
    </repositories>
  </profile>
</profiles>

<servers>
    <server>
      <id>github</id>
      <username>[USERNAME]</username>
      <password>[TOKEN]</password>
    </server>
  </servers>
</settings>
```

where ```USERNAME``` - GitHub username, ```TOKEN``` - GitHub personal access token.
 More about token here - https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token

* **Clone** this repository to local storage
* **Create** new branch for your changes
* **Write** your openApi specification in ```src/main/resources/sandboxOpenApiSchema.yaml```
* **Create** pull request  and wait for approval 

When the pull request is approved, when you merge your pull request, GitHub Actions will publish the package automatically.
 
## How to use package

* **Create** ```settings.xml``` file (if not exist)
* **Include** package like a common maven dependency in your project: 
```
<dependency>
  <groupId>com.sandbox</groupId>
  <artifactId>rest-api</artifactId>
  <version>0.0.1-SNAPSHOT</version>
</dependency>
```