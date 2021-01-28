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
1. polls/views.py
~~~python
from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
~~~

2. polls/urls.py
    - URLconf 생성 (뷰 호출) - polls 디렉토리에서 URLconf를 생성하려면, **urls.py** 파일을 생성
~~~python
from django.urls import path

from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
~~~

3. mysite/urls.py
    - 최상위 URLconf 에서 polls.urls 모듈을 바라보게 설정
    - 다른 URL 패턴을 포함할 때마다 항상 include()를 사용해야 합니다. admin.site.urls가 유일한 예외
~~~python
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
]
~~~

4. path 함수 기능
- route, view, kwargs, name 4개의 인수 포함

## :four: 모델 생성/활성화/테이블 등록
- 모델 생성 : polls/models.py
~~~python
from django.db import models


class Question(models.Model):
    question_text = models.CharField(max_length=200)
    pub_date = models.DateTimeField('date published')


class Choice(models.Model):
    question = models.ForeignKey(Question, on_delete=models.CASCADE)
    choice_text = models.CharField(max_length=200)
    votes = models.IntegerField(default=0)
~~~

- 모델 활성화
~~~python
# 가장 먼저, 현재 프로젝트에게 polls앱이 설치되었다고 등록해야 함.
# mysite/settings.py -> INSTALLED_APPS에 'polls.apps.PollsConfig' 추가

INSTALLED_APPS = [
'polls.apps.PollsConfig',
'django.contrib.admin',
'django.contrib.auth',
'django.contrib.contenttypes',
'django.contrib.sessions',
'django.contrib.messages',
'django.contrib.staticfiles',
]
~~~

Django는 polls 앱이 포함된 것을 알게 되었습니다. 다른 명령을 내려봅시다.
~~~commandline
> python manage.py makemigrations polls
~~~
다음과 같은 결과가 나옵니다.
~~~commandline
Migrations for 'polls':
polls\migrations\0001_initial.py
- Create model Choice
- Create model Question
- Add field question to choice
~~~
makemigrations 을 실행시킴으로서, 당신이 모델을 변경시킨 사실과(이 경우에는 새로운 모델을 만들었습니다) 이 변경사항을 migration으로 저장시키고 싶다는 것을 Django에게 알려줍니다.

마지막으로, migrate 명령을 통해 아직 적용되지 않은 마이그레이션을 모두 수집해 이를 실행하며(Django는 django_migrations 테이블을 두어 마이그레이션 적용 여부를 추적합니다) 이 과정을 통해 모델에서의 변경 사항들과 데이터베이스의 스키마의 동기화가 이루어집니다.
~~~commandline
> python manage.py migrate
~~~