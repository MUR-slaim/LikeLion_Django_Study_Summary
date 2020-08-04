<1>

= Github 기초
목차 : Github 소개, Github 환경설정, 레포지토리 생성 후 푸시

github : git을 모아놓은 곳, git은 파일의 변천사(코드의 변화)를 저장한 것.
         어디서 오류가 난건지 한번에 파악가능하다.
         개발자의 포트폴리오 역할

git 다운로드 -> git bash 다운로드 -> github 계정생성

VScode에서
         git init
         git remote add origin 레포지토리 주소
         git add .
         git commit -m "(원하는 내용)"
         git push origin master
라고 입력하면 된다. 만약 변경사항이 있으면 add .부터 다시 하면 된다.
        
= Netlify를 이용한 배포

정적 페이지와 동적페이지, 동적페이지는 정보가 변한다.
Github 연동 호스팅으로 Netlify에서 배포가 가능해진다.
Netlify 홈페이지에서 github으로 로그인한 다음 시키는 대로 하면된다.
매우 간단!

= Github 협업
목차 : 자주 사용하는 Git 명령어, Github를 사용한 협업


         git branch 브랜치명
          : 새로운 브랜치를 생성
         git checkout 브랜치명
          : 해당 브랜치로 이동
         git push origin 브랜치(대부분 master 쓴다)
          : 원격 저장소의 특정 브랜치에 프로젝트 저장
         git pull origin 브랜치
          : 원격 저장소의 특정 브랜치에서 변경사항 pull 해오기
         git clone http://원격저장소 주소.git
          : 원격 저장소에 있는 파일 전체 복사
         git status
          : git 저장소의 상태를 확인
         git init
          : git 저장소를 초기화
         git remote add origin 레포지토리 주소
          : 원격 저장소 연결
         git add .
          : 폴더에 변경된 모든 파일 staging area에 올리기
         git commit -m "(원하는 내용)"
          : 유사시 돌아갈 수 있는 저장소의 체크 포인트 생성

 - 협업은 이렇게 진행이 된다.

 1. 원격 저장소 생성
 2. 팀원을 Collaborator로 추가
 3. 초기 프로젝트 push
 4. 팀원들의 로컬에 프로젝트 pull
 5. 팀원 각자의 브랜치를 생성하여 작업
 6. 브랜치에 작업한 내용을 pull
 7. master와 merge 하기전 pull request
 8. Pull request 확인 후 Master 와 merge
 
 위의 명령어를 상황에 맞게 사용하면 된다.

 - FORK 협업

 1. 작업 하고 싶은 Repository fork 해오기
 2. 자신의 로컬에서 작업
 3. 변경사항을 자신의 브랜치에 PUSH
 4. 원본 레포지토리 소유자에게 Pull request 요청
 5. 소유자가 pull request를 승인하여 merge 하면 자동으로 collaborator 추가
 
 위의 명령어를 상황에 맞게 사용하면 된다.
