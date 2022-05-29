# git 기본 개념
* https://backlog.com/git-tutorial/kr/intro/intro1_2.html

* Git 영역

(1) Working Directory (Local)

    : 개인 코드 작성

(2) Staging 영역

    :​ git add 를 통해서 수정된 코드를 올리는 영역

(3) Repository

    : ​ git commit 을 통해서 최종 수정본을 제출

* 브랜치 설명 시각화: https://steady-coding.tistory.com/280

# GIT 기본 명령어
* https://psklog.tistory.com/7

----------------------------------
# git 설치

1. 윈도우에 git 설치하기 (운영체제에 맞추어 설정)
    * 참고: https://taewow.tistory.com/13
    * 다운로드 주소: https://git-scm.com/download/win
2. 'Click here to download' 클릭
3. 설치된 파일 실행
4. setup 설정: 기본 default로 진행
    * select distination location : 설치될 경로 지정
    * choosing the default editor used by git: 에디터 선택
         - use vim(기본 default) 선택(주로 사용하는 에디터가 있다면 변경 가능)
    * Adjusting the name of the initial branch in new repositories: 기본 branch 설정
      Override the default branch name for new repositories 선택
    * Adjusting your PATH environment: CMD 설정
        - Git use fit from git bash only 선택: Git bash에서만 사용
5. git 설치: install click

# 0. GIT Bash 실행 및 기본 환경설정(config)

1. 윈도우에 설치된 git bash 열기: command에서 환경설정 진행
2. 사용자 이름/이메일 등록
```
$git config --global user.name "a0lim"
$git config --global user.email "[repository 주소]"
```
3. 사용자 이름/이메일 등록 확인
```
$git config --list
```

# 새로운 GIT 저장소 생성
1. github 페이지에서 원격 저장소 생성
      * git hub 페이지 -> Your repositories 클릭 -> New 클릭-> Repository name에서  [새 원격 저장소의 이름] 입력 -> Create repository 클릭
2. 로컬 저장소 생성
      * 윈도우에서 원하는 파일 주소에서 오른쪽 클릭 -> Git bash here 클릭
3. git bash CMD에서 원격 저장소와 로컬 저장소 연결
      * 참고: 새 저장소에서 안내되는 명령어
1. 1. 저장소에 새 파일(README.md) 만들기
 ```
 echo "# [새 원격 저장소의 이름]" >> README.md 
 // Reinitialized existing Git repository in C:
 ```
 * 다른 방법:
      - $ touch [새 원격 저장소의 이름]

3. 2. 원격 저장소의 디렉터리 초기화 및 .git 폴더 생성
```
$get init
````
            * 폴더 이름을 다르게 지정하는 법: $get init [새 이름]
      3. 3. 저장소 상태 확인: branch 이름, commit 상태 
```
$get status
//On branch master

//No commits yet

//Untracked files:
//  (use "git add <file>..." to include in what will be committed)
//    README.md

//nothing added to commit but untracked files present (use "git add" to track)
````````````
      
      3. 3. 현재 브랜치의 커밋 전 단계 등록
      
```
$ git add README.md
```
* add 뒤에 .: 모두 커밋
      3. 4. 커밋 작성
```
git commit -m "[커밋 내용]"
```
      3.5. 브랜치 연결
```
git branch -M main
```

# Git 저장소 pull/push
0. git bash 기본 환경설정
```
$git config --list
$git config --global user.name "a0lim"
$git config --global user.email "[repository 주소]"
```
1. 깃을 초기화 시켜 로컬 저장소 생성
```
$ git init 
```
2. local과 git repository 연결
```
$ git remote add origin http://github.com/a0lim/TIL.git
```
2-1. ERROR
```
remote origin already exists. ## branch의 remote인 origin이 이미 존재(중복)

$ git remote remove origin ## remote origin의 기존 연결을 끊음
-> 이후 2번으로 돌아가기
```
3. git 확인
```
$ git status 

On branch main # main branch 사용

No commits yet # commit 안 함(local 저장이 안 되어있는 상태) 

nothing to commit (create/copy files and use "git add" to track) # local 저장소에 파일 없음

```
3-1. ERROR
```

```
4. remote branch의 연결 확인
```
$ git remote -v

origin  http://github.com/a0lim/TIL.git (fetch)
origin  http://github.com/a0lim/TIL.git (push)
```
5. git branch 확인
```
$ git branch

* main
... # branch 목록 리스트 
```
5-1. ERROR
```
```
6. 
```
$git add .
$ git commit -m “[commit 내용]”
```
7. pull(git repositoㄱy 자료를 local repository로 내려받음)
```
$ git pull origin master
```

----------------
# 참고
* 브랜치 관련 : https://goddaehee.tistory.com/274?category=381481
* CMD 명령어 : https://simuing.tistory.com/entry/Git-Bash-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%95%EB%A6%AC
   -cd -> 
*  원격 저장소 URL 변경하기 : https://youngjinmo.github.io/2019/09/git-change-remote-branch-url/
*  로컬 저장소의 경로 변경: https://sedangdang.tistory.com/147
*  로컬: https://stackoverflow.com/questions/24114676/git-error-failed-to-push-some-refs-to-remote


** 확인 코드들
$ git remote -v
$ git log
$ git status
$ git branch
$ ls : [ANACONDA] 파일 설치 경로 확인

# ERROR 모음
* Merge branch 'main' of https://github.com/a0lim/TIL : 브랜치 merge하기
* Git refusing to merge unrelated histories on rebase : history 반영 안됨
   - $git pull origin branchname --allow-unrelated-histories
* git error: failed to push some refs to remote: 기존 pull 이후 push 진행
   - $git pull --rebase origin main
git push origin main
* Remote origin already exists:  기존의 연결 끊기
   -  $git remote remove origin
   -  $git remote add origin [새 원격 저장소 url]
* error: pathspec 'main' did not match any file(s) known to git.: git 체크
   - $ git checkout -t -b master origin/master 
* fatal: this operation must be run in a work tree: 디렉토리 안에서 실행-> 상위 폴더에서 실행하기
* fatal: This operation must be run in a work tree: path 확인 (https://stackoverflow.com/questions/9262801/fatal-this-operation-must-be-run-in-a-work-tree)
   - https://code-examples.net/ko/q/30eaeb







** 추가 참고
   - https://github.com/hooong/Github_study
   - https://jhkang-tech.tistory.com/30
   - https://simuing.tistory.com/entry/Git-Bash-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%95%EB%A6%AC
   - 초기화, 삭제 : https://koonsland.tistory.com/94?category=1192234




# vs code 연동
- https://ossam5.tistory.com/169?category=973111
- https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=zeta0807&logNo=220947761377
- https://velog.io/@falling_star3/GitHub-%EA%B9%83%ED%97%88%EB%B8%8C-%EC%9B%90%EA%B2%A9%EC%A0%80%EC%9E%A5%EC%86%8C%EC%99%80-VSCode-%EC%97%B0%EB%8F%99-%EB%B0%8F-%EC%97%B0%EB%8F%99-%ED%99%95%EC%9D%B8-%EB%B0%A9%EB%B2%95git-remote-v
- https://ojui.tistory.com/16
- vs code 에서 파일 업로드: https://opentutorials.org/module/2957/23175
- 


# R 연동
- https://mrchypark.github.io/post/github-rstudio%EB%A1%9C-github-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0/
- https://dlsdn73.tistory.com/657?category=715362







