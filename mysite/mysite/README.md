### :one: Django 프로젝트 생성하기
2
​
3
프로젝트를 생성할 디렉토리로 이동 후.
4
~~~
5
> django-admin startproject mysite
6
~~~
7
~~~
8
project/
9
    mysite/
10
        mysite/
11
            __init__.py
12
            asgi.py
13
            settings.py
14
            urls.py
15
            wsgi.py
16
        manage.py     
17
~~~
18
- mysite : Django 애플리케이션 소스 코드 디렉토리 = 저장소 커밋 관리
19
    1. manage.py: Django 프로젝트와 다양한 방법으로 상호작용 하는 커맨드라인의 유틸리티
20
    2. mysite/ : 디렉토리 내부에는 프로젝트를 위한 실제 Python 패키지들이 저장됩니다. 이 디렉토리 내의 이름을 이용하여, (mysite.urls 와 같은 식으로) 프로젝트의 어디서나 Python 패키지들을 임포트할 수 있습니다.
21
    3. mysite/__init__.py: Python으로 하여금 이 디렉토리를 패키지처럼 다루라고 알려주는 용도의 단순한 빈 파일입니다. Python 초심자라면, Python 공식 홈페이지의 패키지를 읽어보세요.
22
    4. mysite/settings.py: 현재 Django 프로젝트의 환경 및 구성을 저장합니다. Django settings에서 환경 설정이 어떻게 동작하는지 확인할 수 있습니다.
23
    5. mysite/urls.py: 현재 Django project 의 URL 선언을 저장합니다. Django 로 작성된 사이트의 《목차》 라고 할 수 있습니다.
24
    6. mysite/asgi.py: An entry-point for ASGI-compatible web servers to serve your project.
25
    7. mysite/wsgi.py: 현재 프로젝트를 서비스하기 위한 WSGI 호환 웹 서버의 진입점입니다.