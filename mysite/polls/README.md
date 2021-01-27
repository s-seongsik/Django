## :one: Django APP 기본 디렉토리 생성 

~~~commandline
> python manage.py startapp polls
~~~
프로젝트 디렉토리 안에 **polls**의 디렉토리를 생성하고 펼치면 아래와 같습니다.
~~~
mysite/
    mysite/
        __init__.py
        asgi.py
        settings.py
        urls.py
        wsgi.py
    manage.py
    polls/
        __init__.py
        admin.py
        apps.py
        migrations/
            __init__.py
        models.py
        tests.py
        views.py
~~~
해당 구조는 어플리케이션의 기본 뼈대가 되어줍니다.

## :two: 어플리케이션 등록
어플레이케이션을 생성하고 나면 장고에 사용한다고 등록을 해야한다. 이 역할을 수행하는 파일이 
**mysite/settings.py** 입니다. 해당 파일에서 INSTALLED_APPS에 'polls'를 추가합니다.
단순히 'polls' 모듈 이름을 등록해도 되지만 
> polls.apps.PollsConfig 설정 클래스 이름으로 등록하는 것이 보다 정확한 방법입니다.
~~~python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'polls.apps.PollsConfig'
]
~~~

## :three: 첫 번째 뷰 작성 및 실행
> 1. polls/views.py
> ~~~python
> from django.http import HttpResponse
> 
> def index(request):
>     return HttpResponse("Hello, world. You're at the polls index.")
> ~~~

> 2. URLconf 생성 (뷰 호출) - polls 디렉토리에서 URLconf를 생성하려면, **urls.py** 파일을 생성
> ~~~python
> from django.urls import path
> 
> from . import views
> 
> urlpatterns = [
>     # 하위 URL 추가가능
>     path('', views.index, name='index'),
> ]
> ~~~