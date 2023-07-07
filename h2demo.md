---
marp: true
theme: default
class: invert
---

## H2 DATABASE DEMO IN SPRINGBOOT :leaves:

Harist Islami | Java Developer

<br>
<br>

###### Friday | 07/07/2023

---

## About me

![bg left height:4in](photo.jpg)

###### <b><em>HARIST</em></b> ISLAMI | Java Developer Project

---

## WHAT WILL DO

<li> H2 Database Demo In General
<li> How to implement H2 Database in existing project

---

## H2 Database Demo In General

---

### What Dependency do you need ?

<br>

```xml
  <dependency>
      <groupId>com.h2database</groupId>
      <artifactId>h2</artifactId>
      <scope>runtime</scope>
  </dependency>
```

---

### What properties should we use ?

<br>

```properties
  spring.datasource.url=jdbc:h2:mem:tsetdb;MODE=MSSQLSERVER;DATABASE_TO_UPPER=FALSE
  spring.datasource.driverClassName=org.h2.Driver
  spring.datasource.username=sa
  spring.datasource.password=
  spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
  spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.H2Dialect
  spring.jpa.hibernate.ddl-auto=update
```

---

### What if i use yaml/yml instead properties ?

<br>

```yaml
spring:
datasource:
  username: sa
  url: jdbc:h2:mem:tsetdb;MODE=MSSQLSERVER;DATABASE_TO_UPPER=FALSE
  driverClassName: org.h2.Driver
  password: ""
jpa:
  properties:
    hibernate:
      dialect: org.org.hibernate.dialect.H2Dialect
  database-plateform: org.hibernate.dialect.H2Dialect
  hibernate:
    ddl-auto: update
```

---

# <div style="text-align: center;">Easy right ? :thinking: </div>

#### <div style="text-align: center;">Let's Coding </div>

---

## How to implement H2 Database in existing project

---

### A 'lil bit different for the dependency

<br>

```xml
  <dependency>
      <groupId>com.h2database</groupId>
      <artifactId>h2</artifactId>
      <!-- <scope>runtime</scope> -->
      <scope>test</scope>
      <!-- notice that the scope is changes -->
  </dependency>
```

---

### Why change the scope ?

<br>

<table>
<tr>
<th>Scope</th>
<th>Definition</th>
</tr>
<tr>
<td>Runtime</td>
<td>The dependencies with this scope are required at runtime.</td>
</tr>
<tr>
<td>Test</td>
<td>The dependency isn't required at standard runtime of the application but is used only for test purposes.</td>
</tr>
</table>

<br>

<small><em>Source : https://www.baeldung.com/maven-dependency-scopes</em></small>

---

# <div style="text-align: center;">Easy right ? :thinking: </div>

#### <div style="text-align: center;">Let's Coding </div>

---

## Conclusion

<li> H2 Database is one of the good in-memory database for doing unit-test
<li> For the purpose testing, H2 Database must be provide in pom.xml with <b>scope test</b>

---

# <div style="text-align: center;">Thank you :grin:</div>
