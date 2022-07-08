# git 기본 개념
* https://backlog.com/git-tutorial/kr/intro/intro1_2.html

* Git 영역

(1) Working Directory (Local)

    : 개인 코드 작성

(2) Staging 영역

    :​ git add 를 통해서 코드 내용을 올리는 영역

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
## 1. github 페이지에서 원격 저장소 생성
      * git hub 페이지 -> Your repositories 클릭 -> New 클릭-> Repository name에서  [새 원격 저장소의 이름] 입력 -> Create repository 클릭
## 2. 로컬 저장소 생성
      * 윈도우에서 원하는 파일 주소에서 오른쪽 클릭 -> Git bash here 클릭
## 3. git bash CMD에서 원격 저장소와 로컬 저장소 연결
      * 참고: 새 저장소에서 안내되는 명령어
## 1. 1. 저장소에 새 파일(README.md) 만들기
 ```
 echo "# [새 원격 저장소의 이름]" >> README.md 
 // Reinitialized existing Git repository in C:
 ```
## 3. 2. 원격 저장소의 디렉터리 초기화 및 .git 폴더 생성
```
$git init
````
cf) 폴더 이름을 다르게 지정하는 법: $git init [새 이름]
## 3. 3. 저장소 상태 확인: branch 이름, commit 상태 
```
$git status
//On branch main

//No commits yet

//Untracked files:
//  (use "git add <file>..." to include in what will be committed)
//    README.md

//nothing added to commit but untracked files present (use "git add" to track)
````````````      
## 3. 3. 현재 브랜치의 커밋 전 단계 등록
      
```
$ git add README.md
```
cf) add .: 모든 파일을 커밋

## 3. 4. 커밋 작성
```
git commit -m "[커밋 내용]"
```
      3.5. 브랜치 연결
```
git branch -M main
```
------------------------------------------
# Git 저장소 pull/push
## 0. git bash 기본 환경설정
```
$git config --list
$git config --global user.name "a0lim"
$git config --global user.email "[repository 주소]"
```
## 1. 깃을 초기화 시켜 로컬 저장소 생성
```
$ git init 
```
## 2. local과 git repository 연결
```
$ git remote add origin https://github.com/a0lim/TIL.git
```
#### 2-1. ERROR
```
ERROR: remote origin already exists. ## branch의 remote인 origin이 이미 존재(중복)

$ git remote remove origin ## remote origin의 기존 연결을 끊음  
-> 이후 2번으로 돌아가기
```
## 3. git 확인
```
$ git status 

On branch main ## main branch 사용

No commits yet ## commit 안 함(local 저장이 안 되어있는 상태) 

nothing to commit (create/copy files and use "git add" to track) ## local 저장소에 파일 없음

```
#### 3-1. ERROR
$ git add --force [파일명]
```

```
## 4. remote branch의 연결 확인
```
$ git remote -v

origin  https://github.com/a0lim/TIL.git (fetch)
origin  https://github.com/a0lim/TIL.git (push)
```
## 5. git branch 확인
```
$ git branch
* main
... # branch 목록 리스트 
cf) $ git branch -a ## 로컬/리모트 저장소의 모든 branch 정보
    $ git branch -v ## 로컬 branch의 정보 + 마지막 커밋 내역
    $ git branch -r ## 리모트 저장소의 branch 정보

```
6. 
```
$git add .
$ git commit -m “[commit 내용]”
```
7. pull(git repository 자료를 local repository로 내려받음)
```
$ git pull origin main
cf) $ git pull origin main --allow-unrelated-histories ##
```
#### 7-1. ERROR
fatal: The current branch main has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin main

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.

```
git push --set-upstream origin main ## 파일을 강제로 push
```
------------------
# PULL/PUSH 실행 취소(이전 커밋으로 돌아가기)
## reset / revert / checkout
* reset : 시간을 아예 과거의 특정 사건(commit)으로 되돌린다.
* revert : 현재에 있으면서 과거의 특정 사건(commit)들만 없던 일로 만든다. 이전의 commit 내역을 남겨두고 새로운 commit을 생성하면서 과거로 돌아간다.
* checkout : 브랜치 전환

### 0. 커밋 ID 확인
```
$ git log --online

65d7b0d (HEAD -> main) Merge branch 'main' of https://github.com/a0lim/Python_Study_2022_05  ## 커밋 번호: 앞의 '65d7b0d', '88e707c'
88e707c feat: git pull
```
### 1-1. reset

```
$ git reset --soft [commit ID] 
$ git reset --mixed [commit ID]
$ git reset --hard [commit ID]
$ git reset HEAD~10 
$ git reset HEAD^
cf) soft : commit된 파일들을 staging area로 돌려놓음. (commit 하기 전 상태로)
    mixed(default) : commit된 파일들을 working directory로 돌려놓음. (add 하기 전 상태로)
    hard : commit된 파일들 중 tracked 파일들을 working directory에서 삭제한다. (Untracked 파일은 여전히 Untracked로 남는다.)
    HEAD~취소할커밋수 : 현재로부터 원하는 만큼의 커밋이 취소된다.
    HEAD^ : 가장 최근의 커밋이 취소된다. (기본옵션 mixed)
```
### 1-2. revert
```
* revert
$ git revert [과거로 돌아갈 시점의 커밋 ID]
```
### 1-3. checkout
: 특정 파일 복구가 가능
```
# 커밋하지 않아서 원격저장소에 push되지 않은 경우
git ls-files --delete ## 단일 파일인 경우
git ls-files --deleted | xargs git checkout -- ## 다수의 파일인 경우

# 커밋 후 원격저장소에 push된 경우
git rev-list -n 1 HEAD -- [복구하고자 하는 파일의 이름] ## 바로 이전 커밋으로 복구하는 경우임, 옵션 변경 가능
```

### 참고
* reset/revert : https://velog.io/@njs04210/Git-reset%EA%B3%BC-revert-%EC%95%8C%EA%B3%A0-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0#:~:text=1.%20%EA%B0%9C%EB%85%90(%EC%B0%A8%EC%9D%B4%EC%A0%90),-%EC%9D%BC%EB%8B%A8%20%EA%B0%84%EB%9E%B5%ED%95%98%EA%B2%8C&text=reset%20%3A%20%EC%8B%9C%EA%B0%84%EC%9D%84%20%EC%95%84%EC%98%88%20%EA%B3%BC%EA%B1%B0,commit)%EB%93%A4%EB%A7%8C%20%EC%97%86%EB%8D%98%20%EC%9D%BC%EB%A1%9C%20%EB%A7%8C%EB%93%A0%EB%8B%A4.
* checkout: https://devlimk1.tistory.com/124

# CLONE: 특정 파일을 복사함
## 0. config
* git bash 위치: 새 repository/directory
```
$ git config --global user.email "기존의 repository"
$ git config core.sparseCheckout true ## sparse 환경
$ git init
```
## 1. remote 설정
```
$ git remote add -f [remote] [기존의 repository(directory는 불가)]

$ git remote add -f origin https://github.com/a0lim/TIL

```
## 2. 파일 복사
```
$ echo "[복사할 파일의 하위 경로 주소]" >> .git/info/sparse-checkout ## 단일 파일도 가능(뒤에 확장자 표시)

$ echo "PYTHON/study_2022_05" >> .git/info/sparse-checkout
```
## 3. 복사된 파일 붙여넣기
```
$ git pull origin main
```

### 참고
* echo: https://earth-95.tistory.com/92
* clone --mirror: repository 이동 및 복사 방법

----------------
# 참고
* 브랜치 관련 : https://goddaehee.tistory.com/274?category=381481
* CMD 명령어 : https://simuing.tistory.com/entry/Git-Bash-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%95%EB%A6%AC
   -cd -> 
*  원격 저장소 URL 변경하기 : https://youngjinmo.github.io/2019/09/git-change-remote-branch-url/
*  로컬 저장소의 경로 변경: https://sedangdang.tistory.com/147
*  로컬: https://stackoverflow.com/questions/24114676/git-error-failed-to-push-some-refs-to-remote

------
## branch 관련 명령어
* $ git branch [새 branch 이름] ## 로컬에 새로운 branch를 생성
* $ git checkout -b [새 branch 이름] ## 로컬에 새로운 branch를 생성 + 해당 branch로 이동
* 원격 저장소에 있는 branch를 가져오기
    - $ git checkout -t origin/[가져올 branch 이름]
    - $ git checkout -b [가져올 branch 이름] origin/[가져올 branch 이름] ## 원격 
* branch 이름을 변경
    - $ git branch --merged ## 이미 merge된 branch를 표시
    - $ git branch --no-merged ## 아직 merge가 되지 않은 branch를 표시
* git branch -d [삭제할 branch 이름] ## 해당 branch를 삭제/아직 merge 되지 않은 커밋이 있는 경우에는 삭제되지 않음
* git branch -m [변경할 branch 이름] [변경될 branch 이름]

## log 관련 명령어: branch의 커밋 이력
* $ git log ## 현재 branch의 커밋 이력 확인
* $ git log -n[숫자] ## 전체 커밋 중에서 최신 n개의 커밋 확인
  (=) $ git log HEAD~[숫자] ## HEAD(보고 있는 커밋)
* $ git log patch[p 도 가능] ## 파일의 수정된 내용 확인
* $ git log --oneline --graph --decorate --all ## 모든 branch 확인  
```
 --oneline : 현재 commit을 한 줄로 요약 
 --graph : commit 옆에 branch의 흐름을 그래프 확인 
 --decorate : 브랜치와 태그 등의 참조를 간결히 확인 (원래는 --decorate=short 옵션을 의미)
 --all : all 옵션이 없을 경우 HEAD와 관계 없는 옵션은 제외하고 확인
```
  - $ git log --oneline ## 간단히 커밋 해시와 제목 확인
  - $ git log --oneline --reverse ## 가장 오래된 커밋부터 확인
  - $ git log --oneline --graph --decorate ## HEAD와 관련된 커밋을 더 자세히 확인   
  - $ git log --author-"[커밋 작성자 이름]" ## 해당 커밋 작성자의 커밋만 확인
  - $ git log --before="[yyyy-mm-dd]" ## 해당 날짜의 이전 커밋만 확인
  - $ git log --grep="[단어]" ## 해당 단어가 포함된 커밋만 확인
* $ git show "[commit_hashcode]" ## 특정 commit의 내용만 확인
   - $ git show "[commit_hashcode]":"[file 이름]" ## 특정 commit에 여러 개의 파일이 있을 때 파일의 내용을 확인
* $ git diff "[commit_hashcode]" "[commit_hashcode]" ## 2개의 commit을 비교해서 변경 사항 확인
   - $ git diff "[commit_hashcode]" "[commit_hashcode]" "[파일 이름]" ## 2개의 commit에서 해당하는 파일의 차이 확인

#### 참고: https://dkmqflx.github.io/development/2021/01/16/git-log/



** 확인 명령어 모음
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
   - $ git checkout -t -b main origin/main  F
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







