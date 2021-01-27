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
-----------------------------
### :four: Django 시작하기
* [STEP1) 프로젝트 생성](https://github.com/s-seongsik/Django/tree/master/mysite)
* [STEP2) 기본 APP 디렉토리 구조 생성하기](https://github.com/s-seongsik/Django/tree/master/mysite/polls)
