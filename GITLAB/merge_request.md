## 1. (IntelliJ에서) 코드 작성

## 2. (IntelliJ Terminal에서) 브랜치 변경
  ```
  $ git checkout [브랜치명]
  
  ex) $git checkout feat/041
  
  cf) $ git checkout -b [브랜치명]
  // 새로운 브랜치 생성 및 해당 브랜치로 변경
  ```
  
## 3. git add 및 commit
  ```
  $ git add .
  $ git commit -m "commit 내용"
  ```
  
## 4. git push
  ```
  $ git push [remote] [branch]
  
  ex) $ git push origin feat/041
  ```
  
## 5. GITLAB Project의 Merge Requests로 이동

## 6. Merge Request
### 6-1. 새로운 Merge Request를 생성하는 경우
1) New merge request 클릭
2) Source branch에서 push한 branch명을 선택(ex. feat/041)
3) Compare branches and continue 클릭
4) Title, Description 작성 (+ Assignee to me 설정)
5) Submit merge request 클릭

### 6-2. 기존 Merge Request에 refactoring을 올리는 경우
1) 기존 Merge Request 클릭
2) comment 작성
3) Comment 클릭
