# SPA(Single Page Application)
* 한(single) page로 구성된 application
* 최초 로드할 때, 웹 어플리케이션에 필요한 모든 정적 리소스들을 한 번에 받아온다. 이후 새로운 페이지 요청이 있을 경우에는 기존과 비교하여 갱신이 필요한 부분만 json 형태로 data를 받아와 binding 한다.

<br>
<br>

# MPA(Multiple Page application)
* 여러(multiple) page로 구성된 application
* 클라이언트가 새로운 페이지를 요청할 때마다(request 시 마다) 서버로부터 정적 리소스를 받아와 전체 페이지를 다시 렌더링한다. 
매번 서버에서 html 문서를 받아오기 때문에 중복되는 데이터가 있을수밖에 없다.
