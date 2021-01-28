## :one: 데이터베이스 연동 (MSSQL)
1. 적절한 데이터베이스 바인딩 설치
#### :link: 참조 : https://pypi.org/project/django-mssql-backend/
    1. Features
        - Django 2.2, 3.0 지원
        - Microsoft SQL Server 2008 / 2008R2, 2012, 2014, 2016, 2017, 2019 지원
        - Django 테스트 스위트의 대부분의 테스트를 통과합니다.
        - SQL Server 용 Micosoft ODBC 드라이버 , SQL Server Native Client 및 FreeTDS ODBC 드라이버 와 호환
   
    2. Dependencies
        - Django 2.2 or newer
        - pyodbc 3.0 or newer
        
    3. Install
        - Install pyodbc and Django
        - Install django-mssql-backend or django-pyodbc-azure
        
2. 데이터베이스 접속 설정
- mysite/settings.py
~~~PYTHON
DATABASES = {
    'default': {
        'ENGINE': 'sql_server.pyodbc',
        'NAME': 'mydb',
        'USER': 'user@myserver',
        'PASSWORD': 'password',
        'HOST': 'myserver.database.windows.net',
        'PORT': '',

        'OPTIONS': {
            'driver': 'ODBC Driver 13 for SQL Server',
        },
    },
}
# set this to False if you want to turn off pyodbc's connection pooling
DATABASE_CONNECTION_POOLING = False
~~~