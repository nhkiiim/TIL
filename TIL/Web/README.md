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
- WAS 단독으로도 정적, 동적페이지 모두를 구현 가능
- Tomcat, JBoss, Jeus, Web Sphere 등

__3. Web Server, WAS를 분리하는 이유__

`자원 이용의 효율성 및 장애 극복, 배포 및 유지보수의 편의성`
- Web Server는 정적 파일들을 WAS 까지 가지 않고 앞단에서 처리해 기능을 분리하는 것으로 서버 부하 방지
- WAS를 통해 사용자의 요청에 따른 동적 컨텐츠를 만들어서 제공해 자원을 효율적으로 사용
- 물리적 분리를 통해 보안 강화 (SSL에 대한 암복호화 처리에 Web Server 사용)
- Web Server에 여러 대의 WAS를 연결해 Load Balancing 가능


#
### SPA / MPA
__(1) SPA (Single Page Application)__
- 한개의 페이지로 구성된 어플리케이션
- 모든 정적 리소스를 최초 한 번에 다운로드, 페이지 갱신 시 필요한 데이터만 전달 받음
- CSR(Client Side Rendering) 방식으로 렌더링
- 즉각적인 반응으로 유연한 UI 제공 가능
- 초기 페이지 로딩에 시간이 걸려 초기 구동 속도 느림

__(2) MPA (Multiple Page Application)__
- 여러개의 페이지로 구성된 어플리케이션
- 새로운 페이지를 요청할 때마다 정적 리소스가 다운로드되고 매번 전체 페이지가 다시 렌더링
- SSR(Server Side Rendering) 방식으로 렌더링
- SEO (검색엔진 최적화) 관점에서 유리
- 요청이 들어올 때 마다 페이지 로딩 필요해 새로고침 됨 


#
### SSR / CSR 
> [장단점 및 고려사항 참고 링크](https://github.com/nhkiiim/code-repository/wiki/Web#spa--ssr--csr-%EC%9E%A5%EB%8B%A8%EC%A0%90-%EB%B0%8F-%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD)

#
### Nginx
