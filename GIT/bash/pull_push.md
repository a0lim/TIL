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
```
$ git add --force [파일명]
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
## 6. git add와 commit
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
