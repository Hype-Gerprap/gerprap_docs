# HYPE - GERPRAP
## Welcome to hype-gerprap docs!

### What you need installed:
- vscode
    - spring boot extensions
    - vue.js extensions
    - mysql extensions
- java jdk 11
- tomcat server
- node.js
- npm
- mysql (localhost)
- mysql workbench


### Get Started:

> Our *spring-boot api* have a connection with *MySQL*, so to run it you will need to create a database on your local Mysql server, you can do this following this steps:

- 1 create a database on mysql workbech:

```
CREATE SCHEMA `db_hype_gerprap` ;
```

- 2 verify the local credential for your mysql server conncetion inside the spring-boot application on *application.properties*, note that the database name needs to be the same created on *step.1* and your user-name and password are an user with priveligies to mysql use the axample abouve as a guid for it:

```
application.description: hype-gerprap
server.port: 8085
spring.jpa.database:MYSQL
spring.datasource.url=jdbc:mysql://localhost:3306/(**db_hype_gerprap - your database name**)?useSSL=false&serverTimezone=UTC&useLegacyDatetimeCode=false
spring.datasource.username=(**root -your user name**)
spring.datasource.password=(**Senha123 - your password**)
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
spring.jpa.hibernate.naming-strategy=org.hibernate.cfg.ImprovedNamingStrategy
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL5Dialect
spring.jpa.hibernate.ddl-auto=create-drop
```

note: We strongly recomend to use *create-drop* as *ddl-auto* on this stage, after the application is running you can use the *update* to persist tables information.

### Swagger OpenAPI:
> If you properly set the api to run on port:8085, start it and use this url to open the *OpenAPI* documentation, that provides an interface to teste crud funcionality and show the entities attributes:

```
http://localhost:8085/swagger-ui.html
```