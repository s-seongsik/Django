# Django 관리자
> 관리자 사이트는 사이트 방문자를 위한 것이 아닌, 사이트 관리자를 위한 기능입니다.
-------------------------

## :one: 관리자 생성하기

관리자 사이트에 로그인 할 사용자 생성
~~~commandline
> python manage.py createsuperuser
~~~

username 입력
~~~commandline
Username (leave blank to use 'seong'): wizcore
~~~

Email 입력
~~~commandline
Email address: seongsik.seo@wizcore.co.kr 
~~~

pass 입력
~~~commandline
password : wizcore!0
Password (again): wizcore!0
The password is too similar to the email address.
Bypass password validation and create user anyway? [y/N]: y
Superuser created successfully.
~~~

생성 전
![image](https://user-images.githubusercontent.com/52439201/106090185-f2097380-616c-11eb-91ba-775fa946f814.png)

생성 후 
![image](https://user-images.githubusercontent.com/52439201/106090233-11080580-616d-11eb-8060-c1aff95183f9.png)