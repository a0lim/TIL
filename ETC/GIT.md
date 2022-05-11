# git 기본 개념

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

# GIT Bash 실행 및 기본 환경설정(config)

1. 윈도우에 설치된 git bash 열기: command에서 환경설정 진행
2. 사용자 이름/이메일 등록
```
$git config --global user.name "a0lim"
$git config --global user.email "[메일주소]"
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
````````````
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
                       
# 새로운 GIT 저장소 생성
* 참고: https://www.lainyzine.com/ko/article/how-to-link-github-remote-


















