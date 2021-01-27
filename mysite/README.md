### :one: Django 프로젝트 생성하기
프로젝트를 생성할 디렉토리로 이동 후.
~~~
> django-admin startproject mysite
~~~
~~~
project/
    mysite/
        mysite/
            __init__.py
            asgi.py
            settings.py
            urls.py
            wsgi.py
        manage.py     
~~~
- mysite : Django 애플리케이션 소스 코드 디렉토리 = 저장소 커밋 관리
    1. manage.py: Django 프로젝트와 다양한 방법으로 상호작용 하는 커맨드라인의 유틸리티
    2. mysite/ : 디렉토리 내부에는 프로젝트를 위한 실제 Python 패키지들이 저장됩니다. 이 디렉토리 내의 이름을 이용하여, (mysite.urls 와 같은 식으로) 프로젝트의 어디서나 Python 패키지들을 임포트할 수 있습니다.
    3. mysite/__init__.py: Python으로 하여금 이 디렉토리를 패키지처럼 다루라고 알려주는 용도의 단순한 빈 파일입니다. Python 초심자라면, Python 공식 홈페이지의 패키지를 읽어보세요.
    4. mysite/settings.py: 현재 Django 프로젝트의 환경 및 구성을 저장합니다. Django settings에서 환경 설정이 어떻게 동작하는지 확인할 수 있습니다.
    5. mysite/urls.py: 현재 Django project 의 URL 선언을 저장합니다. Django 로 작성된 사이트의 《목차》 라고 할 수 있습니다.
    6. mysite/asgi.py: An entry-point for ASGI-compatible web servers to serve your project.
    7. mysite/wsgi.py: 현재 프로젝트를 서비스하기 위한 WSGI 호환 웹 서버의 진입점입니다.