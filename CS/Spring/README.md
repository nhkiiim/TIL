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
