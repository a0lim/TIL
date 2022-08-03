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
