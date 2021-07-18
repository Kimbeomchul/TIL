# Gradle

### Gradle이란
- gradle은 Groovy를 기반으로 한 빌드 도구이다. Ant와 Maven과 같은 이전 세대 빌드 도구의 단점을 보완하고 장점을 취합하여 만든 오픈소스로 공개된 빌드 도구이다.
  + 하지만.. 회사에선 Ant사용 ..
- 의존성 관리를 위한 다양한 방법을 제공하고 빌드 스크립트를 XML 언어가 아닌 JVM에서 동작하는 스크립트 언어 그루비 기반의 DSL(Domain Specific Language)를 사용한다.

### 세팅방법

### build.gradle ( 예시 코드 ) 

```
buildscript {
    repositories {
        mavenCentral()
    }
    ext {
        springBootVersion = '2.1.6.RELEASE'
    }
    dependencies {
        classpath("org.springframework.boot:spring-boot-gradle-plugin:${springBootVersion}")
    }
}

apply plugin: 'java'
apply plugin: 'org.springframework.boot'
apply plugin: 'io.spring.dependency-management'

version = '0.0.1-SNAPSHOT'
sourceCompatibility = '1.8'

repositories {
    mavenCentral()
}

dependencies {
    // 스웨거 사용 의존성.
    implementation 'io.springfox:springfox-swagger2:2.9.2'
    implementation 'io.springfox:springfox-swagger-ui:2.9.2'

    // lombok 관련 의존성
    implementation('org.projectlombok:lombok:1.18.2')
    compile 'org.projectlombok:lombok'
    annotationProcessor 'org.projectlombok:lombok:1.18.12'

    // 스프링 부트 관련 의존성
    compile "org.springframework.boot:spring-boot-starter-web"
    compile('org.springframework.boot:spring-boot-starter-data-jpa')
    compile("org.springframework.boot:spring-boot-starter-jdbc")
    testCompile "org.springframework.boot:spring-boot-starter-test"

    // H2 DB 사용
    runtimeOnly 'com.h2database:h2'

    // mysql 및 mybatis 사용 의존성.
    compile ('mysql:mysql-connector-java')
    implementation 'org.mybatis.spring.boot:mybatis-spring-boot-starter:2.1.0'

    // JPA에서 toEntity를 간편하게 하기 위해 사용.
    compile('org.mapstruct:mapstruct:1.3.0.Beta2')
    compileOnly('org.mapstruct:mapstruct-processor:1.3.0.Beta2')
    annotationProcessor('org.mapstruct:mapstruct-processor:1.3.0.Beta2')

    //Json 바인드
    compile 'org.codehaus.jackson:jackson-mapper-asl:1.9.13'
    compile group: 'org.apache.commons', name: 'commons-lang3', version: '3.4'
    compile group: 'commons-io', name: 'commons-io', version: '2.5'
    compile group: 'org.json', name: 'json', version: '20160810'
}

test {
    useJUnitPlatform()
}

bootJar{
    archiveBaseName ='lotte'
    archiveFileName ='lotte.jar'
    archiveVersion = "0.0.0"

}
```

### application.properties
- 경로 src - main - resources에 저장 
```
server.port = 80

# MyBatis 설정 파일을 로드한다.
mybatis.type-aliases-package=com.study.common.mybatis
mybatis.mapper-locations=mybatis/mapper/*.xml

# DataSource
spring.datasource.url=jdbc:mysql://localhost/myapp
spring.datasource.username=root
spring.datasource.password=root
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# Mysql 
spring.datasource.url=jdbc:mysql://localhost:3308/study?serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=1234
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.datasource.testOnBorrow=true
spring.datasource.validationQuery=SELECT 1

# H2 Database
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console

spring.servlet.multipart.max-file-size=128MB
spring.servlet.multipart.max-request-size=128MB
spring.servlet.multipart.enabled=true
```

