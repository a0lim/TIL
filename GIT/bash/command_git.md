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

## add 관련 명령어
* $ git add -p

#### 참고: https://blog.outsider.ne.kr/1247

## git commit 관련 명령어
* $ git commit -m "commit-title" -m "description"

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
* git push가 안 될 때 / detached HEAD 문제 해결 방법: 임시 branch 생성 및 사용
    - https://aroma-dev.tistory.com/4
