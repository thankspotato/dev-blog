# WSGI 서버

## 개요
**Web Server Gateway Interface Server**로, 웹서버가 동적 페이지 요청을 처리하기 위해 호출하는 서버 <br/>

## WSGI 서버의 종류
- Gunicorm
- uwsgi
<br/>

## 동작 순서
웹 서버에 동적 요청이 발생하면 웹 서버가 위스키 서버(WSGI)를 호출한다. <br/>
위스키 서버는 WSGI application을 호출한다. <br/>
실제 동적 페이지 요청은 결국 WSGI application이 처리한다. (WSGI application에는 Django, Flask가 있다) <br/>
<br/>
WSGI 서버는 웹 서버와 WSGI application 중간에 위치하고 있어, WSGI middleware 또는 WSGI container라 불리기도 한다.<br/>
<br/>
## WSGI applicaion의 호출
장고 프로젝트 생성 시 자동으로 만들어지는 파일이 있는데, projects\mysite\config\wsgi.py <br/>
WSGI 서버는 항상 이 파일을 경유하여 장고 프로그램을 호출한다. <br/>
특별한 경우를 제외하고 해당 파일을 수정할 필요는 없다. <br/>
<br/>
(특별한 경우란 어떤 것이 있을까?) <br/>

// projects\mysite\config\wsgi.py 이미지 첨부 <br/>
// 동작 순서도 그려서 첨부 <br/>

## 정리
- 웹 브라우저의 정적 페이지 요청은 웹 서버가 처리한다. (NGINX와 같은) <br/>
- 동적 페이지 요청은 WSGI 서버에서 WSGI application을 호출함으로써 처리한다. <br/>
- WSGI 서버는 Spring의 WAS 서버와 동일한 개념으로 이해하였다. <br/>
