### Spring Cloud Config

<!-- .slide: data-background="img/background-orange-orig.jpg" -->

---
### Spring Boot Configuration

- @TestPropertySource annotations on your tests.
- Command line arguments.
- Properties from SPRING_APPLICATION_JSON (inline JSON embedded in an environment variable or system property)
- ServletConfig init parameters.
- ServletContext init parameters.
- JNDI attributes from java:comp/env.
- Java System properties (System.getProperties()).
- OS environment variables.

---
### Spring Boot Configuration (2)
- A RandomValuePropertySource that only has properties in random.*.
- Profile-specific application properties outside of your packaged jar (application-{profile}.properties and YAML variants)
- Profile-specific application properties packaged inside your jar (application-{profile}.properties and YAML variants)
- Application properties outside of your packaged jar (application.properties and YAML variants).

---
### Spring Boot Configuration (3)
- Application properties packaged inside your jar (application.properties and YAML variants).
- @PropertySource annotations on your @Configuration classes.
- Default properties (specified using SpringApplication.setDefaultProperties).

---
### Limitations
- Deployment?
- Skalability?
- Microservice Architecture?
- Docker Deployment?
- Distributing Changes?

---
### Spring Cloud Configuration

<img src="img/cloud-config.png">

---
### Configuration
#### bootstrap.yml
```
spring:
    application:
        name: imported-bons-producer
    cloud:
        config:
            uri: http://config-server:8888
```

---
#### environment variables
```
(...)
    environment:
      - "SPRING_APPLICATION_NAME=imported-bons-producer"
      - "SPRING_CLOUD_CONFIG_URI=http://config-server:18888"
```

---
### Merge Rules
- `application.yml`
- `${spring.application.name}.yml`
- `${spring.application.name}-${profile}.yml` or inner profiles
- label/branch/tag
