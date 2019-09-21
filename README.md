This project is to learn how to build a full stack application using Spring Boot with a React frontend. The project is a Kanban board which will help manage issues and tasks.


To use the local H2 database: `localhost:8080/h2-console`

1) If the following error occurs when trying to access the H2 database
`Database "/Users/lucky/test" not found, and IFEXISTS=true, so we cant auto-create it [90146-199] 90146/90146 (Help)
 org.h2.jdbc.JdbcSQLNonTransientConnectionException: Database "/Users/lucky/test" not found, and IFEXISTS=true, so we cant auto-create it [90146-199]`
 
The following StackOverflow step was useful in debugging the issue:
https://stackoverflow.com/questions/57808646/springboot-h2-fails-to-create-db-and-to-login-into-h2-console

The specific step is to modify the `application.properties` file located in `/src/resources/application.properties` and add the contents

`spring.h2.console.enabled=true
 spring.datasource.url=jdbc:h2:~/test;IFEXISTS=FALSE;DB_CLOSE_DELAY=-1
 spring.datasource.driverClassName=org.h2.Driver
 spring.datasource.username=sa
 spring.datasource.password=
 spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
 spring.h2.console.path=/h2-console`