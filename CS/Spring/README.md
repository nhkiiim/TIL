### JAR / WAR

__(1) JAR (Java Archieve)__
- JAVA 어플리케이션이 동작할 수 있도록 자바 프로젝트를 압축한 파일
- Class (JAVA리소스, 속성 파일), 라이브러리 파일을 포함
- JRE(JAVA Runtime Environment)만 있어도 실행 가능
- Spring Boot는 내장 톰캣을 가지고 있어 간단하게 JAR 배포만으로 실행 가능 (Spring Boot 가이드 표준도 JAR)

__(2) WAR(Web Application Archive)__
- JAR파일의 일종으로 웹 애플리케이션 전체를 패키징 하기 위한 JAR 파일
- Servlet / Jsp 컨테이너에 배치할 수 있는 웹 애플리케이션(Web Application) 압축파일 포맷
- 웹 관련 자원을 포함함 (JSP, Servlet, JAR, Class, XML, HTML, Javascript)
- WAR는 웹 어플리케이션 배포를 위해 JAR보다 특정한 디렉터리(WEB-INF, META-INF)와 파일들이 필요
- 외장 WAS나 JSP를 사용해야하는 경우에 사용

#
### application.properties / application.yml 차이
> [Spring Boot 외부 설정값 주입 참고](https://github.com/nhkiiim/code-repository/wiki/Spring#spring-boot-%EC%99%B8%EB%B6%80%EC%97%90%EC%84%9C-%EC%84%A4%EC%A0%95-%EC%A3%BC%EC%9E%85%ED%95%98%EA%B8%B0-springprofilesactive)

__(1) application.properties__
- Key-Value 형식을 사용하여 외부 구성의 속성을 설정
```
spring.datasource.url=jdbc:h2:DB이름
spring.datasource.username=유저이름
spring.datasource.password=비밀번호
```

__(2) application.yml__
- YAML기반으로 외부 구성의 속성을 설정
```
spring:
    datasource:
        url: jdbc:h2:DB이름
        username: 유저이름
		password: 비밀번호
```

#
### VM arguments (VM options)
- VM arguments(VM options)란 JVM에 전달되어 VM의 동작방식 및 시스템 속성을 정의
- X 옵션 : JVM Heap Memory, Permanent Generation , Direct Buffer 크기 지정 등
- D 옵션 : 전역 시스템 속성 정의
- DKey = Value
- 단건조회 : System.getPropertie(String key)
- 전체조회 : System.getProperties()

<br>

__VM arguments 추가 - Eclipse__
- Servers > open launch configuration > Edit Configuration > VM arguments에 원하는 항목 추가

__VM options 추가 - IntelliJ__
- Run/Debug Configurations > 어플리케이션 선택 > Add VM options 메뉴를 활성화 한 뒤 원하는 항목을 추가

<br>

> 사용 예시
```
-Dspring.profiles.active=local -Djasypt.encryptor.password=[복호화키]
```
