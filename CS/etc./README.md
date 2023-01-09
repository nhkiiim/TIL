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
