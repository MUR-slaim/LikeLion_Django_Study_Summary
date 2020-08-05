1. 마스크 알리미 강의 들어가기.

 - 강좌의 목표와 진행방식 : 개념 -> 실습 -> 서비스 만들기
 - 최종 결과물 : 마스크 알리미 서비스
   초록색 : 100개 이상의 마스크가 있는 약국 / 노랑색 : 30~ 90개가 있는 약국 / 빨강색 : 30개 이하인 약국-
 - HTML, CSS, Javascript Git, Github 사용 (ofcourse 라는 사이트에서 공부가능)
 - VisualStudioCode : 코드를 작성하는 전용 메모장
   POSTMAN : API를 테스트하는 도구
   Python3 : 다음 강좌부터 사용할 언어
   Git : 버전관리 도구
   Github : 버전관리도구로 저장한 내용들을 모아두는 클라우드
   
2. HTTP, JSON, API 개념
 - HTTP : Hyper Text Transfer Protocol
          Hyper Text : 참조를 통해 한 문서에서 관련된 다른 문서들로 넘나들며 
                       원하는 정보를 얻을 수 있게 하는 텍스트
          Transfer Protocol : 인터넷을 통해서 정보를 주고받을 때 지켜야하는 규칙
  HTTP의 요청 메소드 : GET : URL에 표시된 리소스를 가져오기
                      POST : Body 에 정보를 담아 서버에 입력
                      PUT : URL에 표시된 리소스와 바꿔치기
                      PATCH : PUT과 다르게 일부만 수정
                      DELETE : URL에 표시된 특정 리소스를 삭제
 - JSON : Java Script Object Notation
          Key : Value 형식, 데이터 교환
          특징 : 기존 XML보다 가볍다.
          많은 프로그래밍 언어가 지원한다.
          전송 시 : 직렬화 과정을 거친다.
          수신 시 : 역직렬화 과정을 거친다.
 - API : Application Programming Interface
 - REST : Representational State Transfer
          REST의 구성요소 : 자원, 행위, 표현.

3. REST API 실습, Open API
 - JSONPlaceholder : Fake online REST API : REST API를 테스트, 프로토타이핑 가능
                     http://jsonplaceholder.typicode.com/
                     URL의 구성 : 프로토콜, 호스트주소, 파일경로, Quert parameter
 - POSTMAN : 실습 진행함
 
4. Javascript
 - 웹페이지를 동적으로 만들 때 사용하는 언어, 객체 기반의 스크립트 언어
 - 할 수 있는 일이 굉장히 많다! 
   Browser API - DOM, 위치정보, audio, 화면공유 등 Browser 에서 제공하는 API들
   2D, 3D 그래픽 작업 - NullSchool
   클라이언트 뿐만 아니라 서버도 JS로 가능 - Node.js
 - 스크립트 언어 + 인터프리터 장식 : 입력 후 바로 결과 확인
                                    브라우저에 내장된 엔진으로 즉시 해석
 - 사용법1 : HTML에서 불러오기. script 태그 사용한다!
   사용법2 : Js파일을 외부에서 불러오기
 - 변수 : 사용가능한 데이터타입 : Boolean, Null, Undefined, Number, String, Symbol, Object
          var : 권장하지 않는 변수 선언 방식  Hoisting, Function scope변수 중복선언가능
          let : block scope 변수
          const : 변하지 않는 데이터를 저장

                     
