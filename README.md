#### :link: Django 공식문서 참고 : https://docs.djangoproject.com/ko/3.1/
#### :link: Django REST API : https://www.django-rest-framework.org/
#### :link: Django Girls : https://tutorial.djangogirls.org/ko/
#### :link: Django 자습 : https://wikidocs.net/book/837
-----------------------------

## :one: Django 설치하기
1. Django를 사용하기 위한 파이썬 버전 지원
~~~
장고 버전	파이썬 버전들
1.11	  2.7, 3.4, 3.5, 3.6, 3.7(1.11.17에 추가됨)
2.0	  3.4, 3.5, 3.6, 3.7
2.1	  3.5, 3.6, 3.7
2.2	  3.5, 3.6, 3.7, 3.8 (added in 2.2.8), 3.9 (added in 2.2.17)
3.0	  3.6, 3.7, 3.8, 3.9 (added in 3.0.11)
3.1	  3.6, 3.7, 3.8, 3.9 (added in 3.1.3)
~~~
- 장고 1.11은 파이썬 2.7을 지원하는 마지막 버전입니다. 파이썬 2.7과 Django1.11에 대한 지원은 2020년에 끝납니다.
대게 새로운 파이썬 버전이 빠르고, 기능도 많고, 더 많은 지원을 하기 떄문에 가장 최근 파이썬 3 버전을 추천합니다.

### :two: Django 설치
~~~
방법 1. 
- Anaconda 설치
- 가상환경생성
- 가상환경 활성화
- conda install Django

방법 2. 
공식 릴리즈 : python -m pip install Django
~~~
- 설치 확인
~~~
print(django.VERSION)
(3, 1, 5, 'final', 0)
print(django.get_version())
3.1.5
~~~
-----------------------------
### :three: 가상환경 생성(window 10)
- Anaconda
- virtualenv(사용, 독립적)

~~~
[python 버전 확인]
D:\Django>python
Python 3.8.3 (default, Jul  2 2020, 17:30:36) [MSC v.1916 64 bit (AMD64)] :: Anaconda, Inc. on win32
Type "help", "copyright", "credits" or "license" for more information.

[virtualenv 설치]
> pip install virtualenv

[가상환경 생성]
가상환경을 생성할 디렉토리로 이동 후 시작.
> virtualenv venv

[가상환경 활성화]
> call venv/scripts/activate

[가상환경 비활성화]
> deactivate
[가상환경 사용법]
- 설치된 python 버전 확인
> python --version

[가상활경 활성화 후 패키지 설치 및 관리]
> pip install 패키지명
> pip list 
등 관련 문법 서치
~~~

### :four: Django 기본 프로젝트 생성
- 프로젝트를 생성할 디렉토리로 이동 후.
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
    Django_env/
~~~
- mysite : Django 애플리케이션 소스 코드 디렉토리 = 저장소 커밋 관리
    1. manage.py: Django 프로젝트와 다양한 방법으로 상호작용 하는 커맨드라인의 유틸리티
    2. mysite/ : 디렉토리 내부에는 프로젝트를 위한 실제 Python 패키지들이 저장됩니다. 이 디렉토리 내의 이름을 이용하여, (mysite.urls 와 같은 식으로) 프로젝트의 어디서나 Python 패키지들을 임포트할 수 있습니다.
    3. mysite/__init__.py: Python으로 하여금 이 디렉토리를 패키지처럼 다루라고 알려주는 용도의 단순한 빈 파일입니다. Python 초심자라면, Python 공식 홈페이지의 패키지를 읽어보세요.
    4. mysite/settings.py: 현재 Django 프로젝트의 환경 및 구성을 저장합니다. Django settings에서 환경 설정이 어떻게 동작하는지 확인할 수 있습니다.
    5. mysite/urls.py: 현재 Django project 의 URL 선언을 저장합니다. Django 로 작성된 사이트의 《목차》 라고 할 수 있습니다.
    6. mysite/asgi.py: An entry-point for ASGI-compatible web servers to serve your project.
    7. mysite/wsgi.py: 현재 프로젝트를 서비스하기 위한 WSGI 호환 웹 서버의 진입점입니다.

- Django_env : 가상환경 디렉토리
-----------------------------