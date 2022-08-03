# rebase 취소
## 1. git log 확인
```
$ git log --oneline
```
## 2. 중복된 commit 중 최신 commit을 확인하고 그 중 가장 먼저 기록된 commit을 찾아 reset 포인트로 잡는다  
* 위 상황에서는 (11b527a)'feat: delete 코딩테스트 and study_2022_05 because of overlap'가 해당됨  
* 단, 이 경우에는 그 이후에 기록된 (478d934), (258c219)는 삭제됨  

### 2-1. ERROR
* 원격 저장소와 로컬 저장소의 commit log가 다른 경우  
![image](https://user-images.githubusercontent.com/104348646/181495456-0e9fccd3-d44e-41c1-9cac-0c9d88186cb2.png)  

- 중복이 더 많은 저장소의 기준에 따름  

## 3. git reset
```
$ git reset --hard [commit ID]
```

## 4. git push
```
$ git push -f origin main
```

참고: https://americanopeople.tistory.com/206
