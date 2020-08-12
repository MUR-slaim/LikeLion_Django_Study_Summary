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
               누구나 쉬운 사용가능, 반응형 CSS 제공, 모든 최신 브라우저와 호환, 
               PC와 모바일 디자인 제공
 - URL 관리는 어떻게? : django의 URL 관리는 urls.py의 urlpatterns에서 담당
                        path의 구조 path('URL', views 내부의 함수, name="url의 이름"),
                        'URL' : 페이지 주소 / ex) introduce/,
                        함수 : url이 불렸을 때 실행할 함수 / ex) views.home
                        name : 해당 path를 대표하는 이름 / ex) name = "home"

 - Template언어 : python 변수, 문법을 HTML에서 쓸 수 있도록 Django에서 제공하는 언어
                  html과 연동하기 위한 변수 : 명사 {{ }} / 동사 {% %}
                  ex) href="{% url 'introduce' %}" : urls.py 의 'introduce' → views.py의 inroduce
 - Static File : 내용이 고정되어서, 응답할 때 파일 그대로 보내주면 되는 파일 / 
                 ex) 이미지, CSS, JS
                 Static : 웹 서비스 위해 개발자가 미리 만들어둔 파일
                 Media : 웹 서비스 이용자가 업로드하는 파일

    = 처리과정 : static 폴더 생성, App 폴더 내에 "static" 폴더 & 파일 생성

Settings.py 
# Static File들이 들어있는 경로
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'App 이름', 'static'
]
# Static File을 모을 directory
STATIC_ROOT = os.path.join(BASE_DIR, 'static')
Static 파일 모으기
터미널에 입력

  python manage.py collectstatic
  Settings.py (Media 설정)
  MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
  MEDIA_URL = '/media/'
  urls.py
  from django.conf import settings
  from django.conf.urls.static import static
urlpatterns = [
   ...
} + static(settings.MEDIA_URL, document_root = settings.MEDIA_ROOT)
HTML에서 사용
{% load static %}

 * github에 없는데 vscode에 새로 추가된 폴더 or 파일은 초록색으로 나옵니다.

 
4. django로 나를 소개해볼게!
 - 목차 : Model 이해, Model과 Database의 연동 이해와 실습, admin 파악
 - Model이란? 데이터에 접속하고 관리하도록 도와주는 객체
 - Model 생성 #모델명의 첫 글자는 무조건 대문자!
              class Designer(models.Model):
               image = models.ImageField(upload_to = 'images/'
               name = models.CharF
                 address = models.CharField(max_length = 255)
                description = models.TextField()
               데이터에 접속하고 관리하도록 도와주는 객체
 - Terminal : DB가 알아듣도록 번역하기
              python manage.py makemigrations (+ App 이름)
              번역한 내용 DB에 저장
              python manage.py migrate (+ App 이름)
 - Admin
 djnago에서 기본 제공
 웹 서비스 관리위함
 = 사용1
  Terminal 
  python manage.py createsuperuser
 = 사용2
  admin.py
  from .models import Designer
  admin.site.register(Designer)
               
               
               
5. django로 나를 소개해볼게 2!
 - 목차 : QuerySet, Method 이해 & 구현, PK, Path Convertor, get_object_or_404 이해
 QuerySet : 전달받은 모델의 객체 목록이다.
           사용! : views.py
 = Model의 존재 알려주기
from models import Designer

 = Queryset을 Templates로 보내기
 def home(request):
 designers = Designer.objects.all()
 return render(request, 'home.html', {'deginers' : deginers})
 - Detail Page 구현
Server에게 특정 객체를 달라고 Request 
이에 대한 URL을 서버에 알림
객체 반환 또는 404 Error 호출
PK (primary Key)
각각의 글 분류
Models에서 생성된 객체들 구분
고유한 키
관계형 Database
Path Convertor
urls.py에서 글마다 path 만들기
여러 객체의 url을 계층적으로 다룰 수 있게 해주는 도구
/profile/객체번호
ex) 페이지 url에 뜸
"www.dreamary.com/profile/1"
"www.dreamary.com/profile/2"
"www.dreamary.com/profile/3"
 - 사용
urls.py
path('profile/<int:designer_id>/', views.detail, name = "detail"),
Template
{% url 'detail' designer.id %}
get_object_or_404
없는 글을 불러오는 경우 / Object(객체) 가져오려는데 없는 경우
❗️ (views.py의 pk변수명) == (urls.py의 변수명) 같아야합니다.
 - HTTP Method
 - 사용
views.py

from django.shortcuts import render, get_object_or_404  

def detail(request, designer_id):
   designer = get_object_or_404(Designer, pk = designer_id)
   return render(request, 'detail.html', {'designer': desginer}


6. django는 중복을 싫어해!

 - URL Include 
App 별로 URL을 관리할 수 있도록 구조화함

App 폴더 내에 urls.py 생성

from django.urls import path
from . Import views

Urlpatterns = [~]
Project/urls.py
from django.urls import path, include

urlpatterns = [
   path('url/', include('app이름.urls'),
]

 - Template 상속하고 중복은 제거
base.html 이용 : project폴더 내 OK / app폴더 내 OK (Django덕)
다른 페이지 내용이 들어올 부분은 {% block %} {% endblock %} 이용
다른 페이지에서는 Extends로 불러옴
사용
Base.html
<!doctype html>
<head>
  <link href={% block link %}
         ~
  {% endblock %}
</head>
<body>
   ~
   {% block content %}
    ~
   {% endblock %}
    ~
</body>
Home.html
{% extends 'base.html' %}

{% block link %}
{% static 'css/home.css' %}
{% endblock %}

{% block content %}
~
{% endblock %}

7. CRUD#1
