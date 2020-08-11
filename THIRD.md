# LikeLion_Django_Study_Summary

1. 장고, 그게 뭐야?
 - HTML CSS Python 에 대한 지식을 미리 공부할 것!
 - 목차 : Framework & Django 개념 이해, MTV 패턴 파악, 강좌를 수강하며 가져야 하는 마음가짐
 - Django : Python 으로 작상된 오픈소스 웹 어플리케이션 프레임워크
   장고의 특징 : Python 기반, MTV 패턴, Admin 기능 제공, 간편한 URL Parsing
 - Framework 란? : 기본적으로 필요한 기능을 갖춰, 원하는 기능 구현에 집중하도록 도와주는 개발환경
 - MTV 패턴 : Model - View - Template
              URLconf URL 경로에 맞춰 View와 Template 연결
              Template : 사용자에게 보여지는 화면
              View : 웹 요청을 받고, 전달받은 데이터를 처리해서 가공
              Model : 데이터베이스에 저장되는 데이터
              

2. Hello, Django
 - 가상환경이란 : 자신이 원하는 Python 환경 구축을 위해 필요한 모듈만 담아놓는 바구니
 - PIP란 : Python으로 작성된 패키지 소프트웨어를 관리하는 패키지 관리 시스템
 - VS Code 단축키 모음 : [터미널 생성] : Ctrl + Shift + '
                         [터미널에서 이전에 썼던 명령어 불러오기] : 터미널에서 위로가는 방향키 누르기
                         [현재 커서 위치의 코드 복사] : Ctrl + D
                         [현재 커서 위치의 코그 이동] : Alt + 위 아래 방향키
 - 가상환경 명령어 모음 : [가상환경 생성] : python -m venv <가상환경 이름>
                         [가상환경 활성화] : 윈도우|
                                             source <가상환경 이름>/Scripts/activate
                                             
                                             Linux, Mac |
                                             source <가상환경 이름>/bin/activate
                         [가상환경 끄기] : deactivate
                         
 - django 명령어 모음 : [django 패키지 설치] : pip install django
                        [django 프로젝트 생성] : django-admin startproject <프로젝트명>.
                                                마지막에 온점을 붙이면 새로운 폴더가 생기지 않습니다.
                        [djanfo app 생성] : python manage.py startapp <app 이름>
                        [djanfo 로컬 서버 시작] : python manage.py runserver
                        
                                 
3. django가 관리하는 법
 - 목차 : Bootstrap 적용, URL/Template 언어 이해 및 구현, Static 파일 이해
 - Bootstrap : Front-End 개발을 빠르고 쉽게 할 수 있는 오픈소스 Framework
               누구나 쉬운 사용가능, 반응형 CSS 제공, 모든 최신 브라우저와 호환, PC와 모바일 디자인 제공
 - 
 
 
 
4. django로 나를 소개해볼게!
 - 목차 : Model 이해, Model과 Database의 연동 이해와 실습, admin 파악
 - Model이란? 데이터에 접속하고 관리하도록 도와주는 객체
 - Model 생성 #모델명의 첫 글자는 무조건 대문자!
              class Designer(models.Model):
               image = models.ImageField(upload_to = 'images/'
               name = models.CharF
               
               
               
5. django로 나를 소개해볼게 2!
 - 목차 : QuerySet, Method 이해 & 구현, PK, Path Convertor, get_object_or_404 이해
