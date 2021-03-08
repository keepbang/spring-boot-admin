## - Spring Boot Admin

Maven
```
        ...
        <dependency>
            <groupId>de.codecentric</groupId>
            <artifactId>spring-boot-admin-starter-server</artifactId>
        </dependency>
        ...
```

gradle
```
        ...
        implementation 'de.codecentric:spring-boot-admin-starter-server'
        ...
```

### In Java Class
```
    @SpringBootApplication
    @EnableAdminServer //Add
    public class SbamoduleApplication extends SpringBootServletInitializer {
    
        public static void main(String[] args) {
            SpringApplication application = new SpringApplication(SbamoduleApplication.class);
            application.addListeners(new ApplicationPidFileWriter());
            application.run(args);
        }
    
        @Override
        protected SpringApplicationBuilder configure(SpringApplicationBuilder application) {
            return application.sources(SbamoduleApplication.class);
        }
    
    }
```

### yml file edit
```
    server: 
        port: 9999
```
