# Rename directiory with histories
* 상황 : 백준 -> baekjoon으로 이름 변경 
* 문제: Commit history가 반영되지 않음

## 0. git filter-repo 설치
* 관리자 모드로 cmd 창 열기  
* pip 설치  
```
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py ## 입력 후 실행
python git-pip.py ## 입력 후 실행
```
* git-fiflter-repo 설치  
```
pip install git-filter-repo ## 입력 후 실행
```
* 설치 확인
```
$ git filter-repo -h ## help 실행
```

![image](https://user-images.githubusercontent.com/104348646/180924001-b43918bf-73de-4de9-ab9e-78d02c29939a.png)

## 1. 이름 변경 with histories
```
$ git filter-repo --path-rename [old name]:[new name]
cf) $ git filter-repo --path-rename 백준:baekjoon
```

### 1-1. ERROR

Aborting: Refusing to destructively overwrite repo history since
this does not look like a fresh clone.
  (expected freshly packed repo)
Please operate on a fresh clone instead.  If you want to proceed
anyway, use --force.
```
$ git filter-repo --force --path-rename [old name]:[new name]
```

## 1-2. ERROR
bash: syntax error near unexpected token `('
```
$ git-filter-repo --path-rename 환경 설정(config) 및 설치:config_set ## problem: 이름에 space와 (, )이 포함되어 있어 에러가 발생함
$ git-filter-repo --path-rename '환경 설정(config) 및 설치':config_set ## 문제가 있는 파일 이름에 '' 넣기
```


* 참고
    - git filter-repo: https://github.com/newren/git-filter-repo/blob/main/INSTALL.md
    - pip 설치: https://mrkim.tistory.com/1
    - git filter-repo 적용: https://stackoverflow.com/questions/2314652/is-it-possible-to-move-rename-files-in-git-and-maintain-their-history#comment120743678_60511341

![image](https://user-images.githubusercontent.com/104348646/179740986-aef664cc-df39-402f-8986-dfd77057106a.png)


## 특정 파일의 log만 보기
```
$ git log --oneline -M --follow -- /C/Users/aylim/Desktop/공부/git_local/TIL/baekjoon
```
