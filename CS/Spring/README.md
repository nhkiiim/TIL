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

#
### Jasypt
> [공식 문서 및 사용 예시](https://github.com/nhkiiim/code-repository/wiki/Spring#jasypt)
- 프로젝트에서 DB 접속 정보와 같이 외부에 노출 되면 안되는 정보들을 암호화해주는 자바 라이브러리
- 간편한 단방향(다이제스트) 및 양방향 암호화 기술을 제공
- 기본 Java VM뿐만 아니라 모든 JCE(자바 암호화 확장) 공급자와 함께 사용할 수 있는 개방형 API
-  Spring에서 쉽게 사용할 수 있도록 설계되어 싱글톤 지향 환경에서 동기화 걱정 없이 사용 가능
```
spring.datasource.password=ENC(hReucCsYHuu6DBKL4LJvdUQGgL4JGar+)
```

#
### Interceptor
> 권한 체크 공통 로직에 활용

> [참고 자료 및 필터와 차이](https://github.com/nhkiiim/code-repository/wiki/Spring#interceptor)

- Spring이 제공하는 기술로, 디스패처 서블릿(Dispatcher Servlet)이 컨트롤러를 호출하기 전과 후에 요청과 응답을 참조하거나 가공할 수 있는 기능을 제공
- org.springframework.web.servlet.HandlerInterceptor 인터페이스를 구현해 사용 가능
- org.springframework.web.servlet.handler.HandlerInterceptorAdapter 추상클래스를 오버라이딩해 사용 가능

__(1) preHandle()__
- 컨트롤러가 호출되기 전에 실행됨
- 컨트롤러가 실행 이전에 처리해야 할 작업이 있는경우 혹은 요청정보를 가공하거나 추가하는경우 사용

__(2) postHandle()__
- 핸들러가 실행은 완료 되었지만 아직 View가 생성되기 이전에 호출
- 컨트롤러를 호출된 후에 처리해야 하는 후처리 작업이 있을 때 사용
- ModelAndView 타입의 정보가 제공되는데, 최근에는 Json 형태로 데이터를 제공하는 RestController를 만들면서 자주 사용되지는 않음

__(3) afterCompletion()__
- 모든 View에서 최종 결과를 생성하는 일을 포함한 모든 작업이 완료된 후에 실행
- 요청 처리중에 사용한 리소스를 반환해주기 좋은 메서드

