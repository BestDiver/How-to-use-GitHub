# Github 기초 사용방법

1. Git 초기설정

2. Git 기본 명령어
   
   1. git init
   
   2. git status
   
   3. git add
   
   4. git commit
   
   5. git log
   
   6. 한 눈에 보는 Git 명령어

---

## 1.Git 초기설정

**최초 1번만 실행**

1. 누가 커밋 기록을 남겼는지 확인할 수 있도록 이름과 이메일을 설정
   
    $git config --global user.name "이름"
   
   $ git config --global user.email "메일 주소"

2. 작성자가 올바르게 설정되었는지 확인

$ git config --global -l

or

$ git config --global --list

---

## 2.Git 기본 명령어

**(1)$ git init**

현재 작업중인 디렉토리를 Git으로 관리한다는 명령어

--- 

**cd** Desktop/start/git_practice 으로 내가 원하는 위치까지 들어가기(대문자 조심)

**cd** .. (부모 디렉터리로 이동)

**cd** - (바로 이전 디렉터리로 이동)

**cd**  (맨 첫번째 디렉터리~로 이동)

$ ls -a (-a : all 옵션. 숨김 파일까지 모두 보여줍니다) *엘에스 에이*

$ mv text.txt folder (text.txt를 folder 폴더 안에 넣을 때)

$ touch text1.txt (빈파일 생성)

$ mv text1.txt text2.txt (text1.txt의 이름을 text2.txt로 바꿀 때)

**(2)$ git status**

파일의 현재 상태를 알려주는 명령어

$ touch text.txt (빈파일 생성)

$ mkdir folder (디렉터리 생성)

### 파일에 수정사항이 있을 경우

echo kevin >> a.txt (한 후 git status)[a는 파일 이름]

1. 커밋할 3개 파일이 준비되어 있는데 a는 수정사항이 있다.

2. 지금 상황은 3개의 파일이 staging area에 있고

3. working directory에 modified된 a.txt도 있는 상태다. git status 확인

4. 수정된 파일을 다시 add 하기
   
   git add a.txt  한 후에 git status 해보기
   
   ### 파일 unstage하기
   
   1. 메시지 보면 git rm --cached <file> 을 통해서 unstage 시킬수 있다는
      
      문구도 참고로 알려준다
   
   2. 그리고 **( git reset -- *.txt )** 이렇게 모두 unstaged로 내릴수 도 있다
      
      git add . 으로 모두 스테이징 시키자
      
      참고로 rm은 원격저장소의 파일을 삭제하고 그리고 동시에 staging area에서
      
      파일을 내리기 위해서 사용한다. 그런데 --cached 옵션을 넣어 줌으로써
      
      스테이징에서 파일만 내리겠다고 적어 준 것이다.
      
      따라서 단순하게 스테이징에서 파일을 내릴때는 주고 rm 보다 reset을 많이 사용하지만 원격저장소에서 파일을 삭제해서 staging area에서 파일을 내릴때는
      
      rm 을 사용한다. (ignore 할때)

**(3) Git add**

working>>>staging area로 파일을 업로드 하는 과정

이제 Untracked 에서 Modified 단계로 넘어감

**(4) Git commit**

staging area에서 git directory로 이동

git directory: staging area에 있던 파일 및 폴더의 변경사항(커밋)을 저장하는 곳

**(5) Git push**

git directory의 파일 및 폴더를 외부 저장소(GitHub)로 옮기는 작업

GitHub가입 후 url주소를 받아 git push https://github.com/BestDiver/How-to-use-GitHub.git형태

**(6) Git clone**

외부저장소의 파일을 내 집이나 다른 곳으로 옮기고 싶을 때 **최초 1회만 시행**하는 것으로 **폴더를 만들지 않고 바탕화면에 바로 만들 시 바탕화면에 파일이 꽉 차는 대참사가 날 수 있다...**

**(7) Git pull**

최초 시행 후는 Git pull ~~~~url주소를 사용하여 변경된 부분만 볼수 있다.
