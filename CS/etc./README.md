### Nexus
> [넥서스 설치 공식 문서](https://help.sonatype.com/repomanager3)
- Sonatype 에서 만든 무료 사설 Maven 저장소
- Maven Repository에서 jar 파일을 다운받아오지 않고 Nexus Repository를 통해 따로 관리
- 외부 리포지토리에 접속하기 어려운 경우 Proxy 역할 제공 가능
- Maven에 올라와 있지 않은 자료들은 효율적으로 관리 가능
- 협업 시 공통 라이브러리들을 공유

```gradle
// build.gradle에 Maven 저장소 설정 가능
buildscript {
    repositories {
        maven { url = "http://nexus.pangtrue.kr:8081/nexus/content/groups/public/" }
    }
}
```

#
### Keycloak
> [keycloak 참고 링크](https://github.com/nhkiiim/code-repository/wiki/etc.#keycloak)
- ID 및 액세스 관리 솔루션을 제공하는 오픈소스
- 인증(Authentication)과 인가(Authorization)을 쉽게 해주고 SSO(Single-Sign-On)을 가능하게 해주는 오픈소스
- OpenID Connect, OAuth 2.0 및 SAML 2.0의 세가지 프로토콜을 지원
- 웹 기반 GUI로 관리자 콘솔을 제공
- 관리자 패널에서 설정을 통해 소셜 ID를 사용 가능 (google, twitter, stack overflow ..)
