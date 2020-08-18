# LikeLion_Django_Study_Summary

# 1. 자소설 닷컴 만들기

 - CRUD : Create Read Update Delete
 - ON FOCUS : "django 답게 코딩하기." "데이터, 데이터베이스, 모델에 집중!"
 - 장고기능 : DJango 공식 깃허브  https://github.com/django 공식 문서  https://docs.djangoproject.com/ko/3.0/


# 2. 모델과 데이터베이스

 - 목차 : Model & database 데이터 베이스 살펴보기 모델을 데이터베이스에 반영하기.
 - Django의 Model, Database : SQL 언어 X, ORM 사용
 - 각각의 데이터는  object! column은 목록!
 - 번역파일 생성 : $ python manage.py makemigrations 와 $ python manage.py migrate  
                   파이선 명령 번역 -> 번역파일 남음      데이터베이스를 짜달라구 얘기  

 - Primary Key : AutoField
 - 문자열 : CharField, TextField, SlugField
 - 숫자 : IntergerField, PositiveIntegerField, FloatField
 - 날짜/시간 : DataField, TimeField, DataTimeField
 - 참/거짓 : BooleanField, NullBooleanField
 - 파일 : FileField, ImageField, FilePathField
 
# 3. ModelForm
 - 목차 : ModelForm을 활용한 create, ModelForm 속성 제어, 기본 레이아웃 구성
 - 모델 폼이란  
   : 모델에 대응하는 html폼을 만들어 줌  
   : 데이터를 생성하거나 업데이트가 간편   
   : 폼을 다루는 법을 배워야 함.  
   
    shift + 새로고침 = 반영이 안 될 때 눌러주시오

 - 템플릿 필터  
   장고에서 템플릿 필터라구 검색하면 여러개 뜹니당 활용하세요

# 4. Primary Key
 - Primary Key ( PK ) : 오브젝트를 식별할 수 있는 값, 중복될 수 없는 단일 값  
   = 그 컴활 필기에서 배운 기본키 느낌인 것 같음!  
   = 항상 있어야함  
   = django에서는 PK를 안만들면 자동으로 id가 생성됨 
   = 예를 들면 자소설 닷컴의 ID가 PK입니다
 
 나도 함수 회색상자에 넣구 싶다구 했더니 수아가 방법 알려준거 아래로 차근차근 적어놨음  
 완전 멋있다 고마워 수아야 *^^*

 ```
 my_pk = models.IntergerField(primary_key=True)
 ```
 
 ` `` my_pk = models.IntergerField(primary_key=True)`  
 
 ``` ``` ``` my_pk = models.IntergerField(primary_key=True)```
 
 <div>
   <div></div> my_pk = models.IntergerField(primary_key=True)
 </div>
 
 ```python
   ```python``` my_pk = models.IntergerField(primary_key=True)
  ```
 > python 색상
 
    my_pk = models.IntergerField(primary_key=True)  
> 스페이스 4번 또는, 탭 두번

>  
>>  
>>>


# 5. USER #1
 - 목차 : USER모델, url상속, 회원가입 구현  
   **회원가입 아마도 정책 알림이 때 쓰지 않을까..**
 - User 모델 : django의 회원관리 시스템을 갖다 쓰자!  
               원래 기능을 분류(앱)해서 사용해주는 것  
 - url 상속 : urls.py를 이용해봅시다~  
 ```
     from django.urls import path  
     urls.py ->  path('', include('main.urls'))  
     import include
 ```
 
# 6. USER #2 
 - 목차 : 로그인, 로그아웃, USER Template Tags
 - 로그인 : django auth을 통해 가져옴 -> 로그인뷰 사용~  
            import LoginView 까먹지 말기....오류.....제발...
 - 로그아웃 : 로그아웃도 로그아웃 뷰를 사용한다! 
  
 ```
 from django.contrib.auth.views import LoginView, LogoutView

urlpatterns = [
    path('signup/', signup, name='signup'),
    path('login/', LoginView.as_view(), name='login'),
    path('logout/', LogoutView.as.view(), name='logout'),
]
```

# 7. Foreign Key

 - 목차 : Foreign Key란, 작성자 추가하기, Permission, Decorator, filter
 - Foreign Key : User 모델 - Jasoseol  1:N 관계 형성!  
   = 얘가 컴활 필기 외래 키인듯
   = User모델의 속성을 가져왕ㅛ
 - Decorator : 로그인했냐
 ```
   from django.contrib.auth.decorators import login_required  
   함수 위에 @login_required(login_url='/login') : 로그인 유효검사 해줌  
```
 - filter : 내꺼  
```
def my_index(request): 
my_jss = Jasoseol.objects.filter(author=request.user) 
return render(request, 'index.html', {'all_jss': my_jss})

```

 # 8. 댓글 만들기
 
 - 목차 : ModelForm & ForeignKey 응용, 댓글 구현 실습
 - 댓글 모델을 만드는 등의 응용을 하면 됩니다.  
   한 사람이 여러개 쓸 수 있으니 이 개념은 ForeignKey~
   
```
class coment(models.Model): 
  content = models.CharField(max_length=100)
  authohr = models.ForeignKey(User, on_delete = models.CASCADE)
  jasoseol = models.ForeignKey(jasoseol, on_delete = models.CASCADE)
```
```
def create_comment(request, jss_id):
    comment_form = CommentForm(request.POST)
    if comment_form.is_valid():
        temp_form = comment_form.save(commit=False)
        temp_form.author = request.user
        temp_form.jasoseol = Jasoseol.objects.get(pk=jss_id)
        temp_form.save()
        return redirect('detail', jss_id)
    

def delete_comment(request, jss_id, comment_id):
    my_comment = Comment.objects.get(pk=comment_id)
    if request.user == my_comment.author:
        my_comment.delete()
        return redirect('detail', jss_id)

    else:
        raise PermissionDenied
```

# 9. 글자수세기
 - 목차 : 웹 자바스크립트, Event, 선택자와 이벤트 핸들러
 - 해당버튼선택 -> 이벤트 감지 -> 로직실행  
   [요소 선택] : querySelector()  
   [이벤트핸들러] : 요소.addEventListener("이벤트", 이벤트를 감지했을 때 실행되는 함수)  
