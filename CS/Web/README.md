### IIS (Internet Information Services, IIS)
> 윈도우에서 Git 서버 구축 시 사용해봄
- 인터넷 정보 서비스로 윈도우에서 사용 가능한 웹서버 소프트웨어
- 윈도우 서버에 기본으로 내장되어 있고 마이크로소프트에서 직접 개발해 제공하는 프로그램으로 윈도우와 호환성이 좋음
- 웹 서버 프로그램에서는 아파치 HTTP 서버와 더불어 잘 알려진 프로그램으로 리눅스에서 아파치라면, 윈도우에서는 IIS가 웹 서버 프로그램을 대표함

#

### Web Server / WAS
__1. Web Server__
- 정적 컨텐츠(.html .jpeg .css 등) 제공
- WAS에 요청 전달 및 클라이언트에 응답 전달
- Apache, Nginx, IIS 등

__2. WAS (Web Application Server)__
- DB 조회나 비즈니스 로직 처리 후 동적 컨텐츠 제공
- 웹컨테이너, 서블릿컨테이너라고도 불림
- 분산 트랜잭션, 보안, 메시징, 쓰레드 처리 등의 기능을 처리하는 분산 환경에서 사용
- Tomcat, JBoss, Jeus, Web Sphere 등

__3. Web Server, WAS를 분리하는 이유__

`자원 이용의 효율성 및 장애 극복, 배포 및 유지보수의 편의성`
- Web Server는 정적 파일들을 WAS 까지 가지 않고 앞단에서 처리해 기능을 분리하는 것으로 서버 부하 방지
- WAS를 통해 사용자의 요청에 따른 동적 컨텐츠를 만들어서 제공해 자원을 효율적으로 사용
- 물리적 분리를 통해 보안 강화 (SSL에 대한 암복호화 처리에 Web Server 사용)
- Web Server에 여러 대의 WAS를 연결해 Load Balancing 가능

#

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

