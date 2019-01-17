# Management Console

> Please raise any issues found with this example in our JIRA:
> https://issues.jboss.org/browse/THORN

## Project `pom.xml`

The project is a normal maven project with `jar` packaging, not `war`.

    <packaging>jar</packaging>

The project adds a `<plugin>` to configure `thorntail-maven-plugin` to
create the runnable `.jar`.

    <plugin>
      <groupId>io.thorntail</groupId>
      <artifactId>thorntail-maven-plugin</artifactId>
      <version>${version.thorntail}</version>
      <executions>
        <execution>
          <goals>
            <goal>package</goal>
          </goals>
        </execution>
      </executions>
    </plugin>

To define the needed parts of Thorntail, some dependencies are added

    <dependency>
        <groupid>io.thorntail</groupId>
        <artifactId>management-console</artifactId>
        <version>${version.thorntail}</version>
    </dependency>
    <dependency>
        <groupid>io.thorntail</groupId>
        <artifactId>management</artifactId>
        <version>${version.thorntail}</version>
    </dependency>

## Running

The container is started.

    mvn package

Then start the server

    java -jar target/example-management-console-thorntail.jar
       

## Use

Open the following URL and you should see the management console UI.

    http://localhost:8080/console

### Adding management hosts

Click on the Add button and enter the following information: 

    Name: Localhost
    Scheme: http
    Hostname: 127.0.0.1
    Port: 9990

Press the Ping button and present the following authentication info:

    User: bob 
    Password: tacos!
 
If it's correctly configured it should present a message saying 
*The management interface is running.*

Click Add and then Connect. You should see the management console UI.
