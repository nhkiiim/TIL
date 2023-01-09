### iframe
- HTML <iframe> 은 중첩된 브라우저를 나타내는 요소로, 현재 문서 안에 다른 HTML 페이지를 삽입할 수 있게 해줌
- 삽입된 Browsing context(탭이나 프레임)은 각각의 세션을 가짐
- HTML5 이전에도 이후에도 <iframe>을 사용하지 않는 것을 권고
- 페이지의 파편화 문제 발생 가능 (검색 엔진 등록 시 frameset 뿐만 아니라 메뉴용 페이지, 콘텐츠용 페이지 까지 함께 크롤링)
```html
<iframe src="삽입할페이지주소" width="너비" height="높이"></iframe>
```
