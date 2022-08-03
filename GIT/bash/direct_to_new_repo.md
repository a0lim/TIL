# 하위 directory를 다른 레파지토리로 분리 with histories

* 가정) A repository의 하위 directory a를 새로운 B repository로 분리

## 0. 새 repository 만들기
* github 원격저장소에서 만들기를 추천

## 1. 기존 repository(A) 실행

## 2. 폴더(a) 복사
```
$ git subtree split - [옮길 폴더 이름] -b [브랜치 이름]
$ git subtree split -p a -b branch

cf) A reopsitory/a/b/c 를 복사하는 경우
    $ git subtree split -p a/b/c -b branch
```

## 3. 새 repository(B) 실행
* 방법 1: B repository의 로컬저장소에서 실행
```
$ cd ../B/ ## 방법 2
```

## 4. git pull 복사된 파일(a)
```
$ git pull ../[기존 repository 이름]/ [브랜치 이름] ## repository만 가능
$ git pull ../A/ branch
```

## 5. 로컬 저장소와 원격 저장소를 연결
```
$ git remote add origin [새 원격 저장소(B) 주소]
```

## 6. git push
```
$ git push origin main
```

* 참고: https://ashortday.tistory.com/58


### 참고
* 특정 파일의 log만 보기: https://kgrz.io/use-git-log-follow-for-file-history.html

* 크롬 앱 사용: https://lumiloves.github.io/2018/06/25/how-to-preserve-file-history-when-renaming-or-moving-in-git
* create new class 사용: https://itpangpang.tistory.com/282
* subtree 사용: https://yh0921k.tistory.com/27
* subtree 사용 2: https://sustainable-dev.tistory.com/119
