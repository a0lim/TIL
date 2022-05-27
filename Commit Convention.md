# angularJS Commit Convention

## Commit Structure
```
   <type>(<scope>): <subject>
   <BLANK LINE>
   <body>
   <BLANK LINE>
   <footer>
```

## Type
  - 단절적 API 변경의 경우: 타입 뒤에 !를 붙임 ex) fix!
  
  - fix: 버그를 고친 경우
  - feat: 새로운 기능을 추가할 경우
  - docs: 문서 수정한 경우
  - ci: CI 설정 파일 수정
  - build: 빌드 관련 파일 수정(빌드시스템에 변화가 있거나 외부 라이브러리를 추가했을 때)
  - perf : 성능 개선(퍼포먼스 측면에서 코드에 변화를 주었을 때)
  - test: 테스트 코드 추가, 테스트 리팩터링 (프로덕션 코드 변경 없음)
  - refactor: 프로덕션 코드 리팩터링(버그나 새로운 기능이 추가하지 않고 코드를 수정하는 경우)
  - style: 코드 포맷 변경, 세미 콜론 누락, 코드 수정이 없는 경우 ex) ';', 들여쓰기 등
)


## Scope: 변경된 부분(함수 이름, 클래스 이름 등)
- animations, common, compiler, compiler-cli, core, elements, forms, http, language-service, platform-browser, platform-browser-dynamic, platform-server ,platform-webworker, platform-webworker-dynamic, router, service-worker, upgrade
- ex) release, changelog
    
## Subject: 제목
- 50자 제한, 소문자로 시작, 마침표 사용 안 함
- 명령어로 작성 ex) change, build, style 등
  
## Body(optional): 본문
- What(무엇), Why(왜), How(어떻게) 에 맞추어 작성
- 72자 제한
  
## Footer(optional): 꼬리말
- 단절적 API 변경의 경우 ex) BREAKING CHANGE: <description>
- 주요 변경 내역 작성: 변경점 (description of the change), 변경 사유 (justification), 마이그레이션 지시 (migration instructions) 언급
- 해결된 이슈 ex) Fixes #234, #123
  
 ------------------------------------------------------------------------------------------------------------
  
  
* readme.md
- 프로젝트명, 프로젝트 소개, 설치 방법, 사용 예제, 개발 환경 설정 방법, 기여 방법, 변경 로그, 라이센스 및 작성자 정보를 포함
- 프로젝트명(Project title): 프로젝트 소개 웹 사이트 추가(heroku, surge.sh, gh-pages 등), 사용한 기수/분야/주제 등의 태그 추가
- 프로젝트 내용(Motivation, Features, Tech/framework used, Screenshots): 프로젝트의 목적/동기/주요 기능 서술, 프로젝트의 실제 데모 추가, (shields.io에서 뱃지 사용)
- 설치 방법(Installation): 최대한 자세하게 작성, 운영체제 별 설치 방법 작성
- 코드 예제(code Example, How to use?, Tests): 설치 이후의 실제 사용 방법 가이드(코드 예제/실제 적용 사례)
- 개발 환경 설정 방법: 사용자가 개발 환경을 올바르게 설정 있는지 확인(명확한 가이드 제시, 개발 의존성 설치와 자동 테스트 슈트 실행)
- 기여 방법: 개발 프로세스와 기여 방법에 관한 명확한 지침 제공
- 로그 변경: 버전 별 변경 사항 확인, 기능개선/수정 내역을 함축적으로 정리
- 크레딧(Credits): 기여한 사람 언급
- 라이센스(License): 디렉터리에 LICENSE.txt 포함 (MIT 라이센스, Apache 2.0 라이센스, ISC 라이센스, BSD 라이센스 등)
- 연락처(Contribute): 팀원들의 깃허브 프로필 링크, 트위터, 이메일 등의 연락처 정보 기입
- Build status, code style, API Reference 등

* 프로젝트 관리
- 실제 프로그램 설계 계획 및 실행: 개발 진행 상황 트래킹, 관리, 문제 해결
- 프로젝트 보드 사용: 보편적인 기능부터 특정 기능 작업, 로드맵을 작성하고배포 체크 리스트을 관리 (깃허브와 연동 간편)
- 이슈 관리: 작성자가 새로운 이슈를 작성 시, 먼저 유형을 선택하고 제시된 양식에 맞춰 작성

* 오픈 소스 기여하기
- OSI의 오픈 소프트웨어 10가지 조건 준수
- 사용 중인 라이브러리, 프레임워크의 깃허브 리퍼지토리를 찾기: 리퍼지토리에 별(star)을 달고 오픈 소스 메인테이너, 컨트리뷰터가 누구인지 찾아 팔로우
- 이슈 고치기 - 풀리퀘스트 보내기 : 일반적인 오픈 소스 기여 방법이다. 이슈 리스트(예: react 이슈리스트 )를 확인하고 직접 고쳐 풀리퀘스트를 보내보자.
- 오탈자 고치기 : 코드로 기여하기 어렵다면 문서나 내 오타를 고치는 것부터 시작하자. 아주 사소한 세미콜론, 따옴표, 맞춤법도 괜찮다.
- 이슈 제기하기 : 버그, 기능 개선 요청, 문서 수정 요청 등 이슈를 제기하거나, 해결 방법을 댓글로 알려주는 것도 오픈 소스에 기여하는 것이다.
- 번역하기 : 공식 문서와 도움말을 한국어 번역해보자. 페이스북 또는 깃허브에서 한국어 사용자 그룹 커뮤니티를 찾아보고 번역 프로젝트에 동참하자.

* 참고
- https://www.conventionalcommits.org/ko/v1.0.0/
- https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines
- https://velog.io/@outstandingboy/Git-%EC%BB%A4%EB%B0%8B-%EB%A9%94%EC%8B%9C%EC%A7%80-%EA%B7%9C%EC%95%BD-%EC%A0%95%EB%A6%AC-the-AngularJS-commit-conventions
- https://velog.io/@skennetho/git-AngularJS-Commit-Convention-%EC%A0%95%EB%A6%AC
- https://sujinlee.me/professional-github/


* 추가
- Git Flow 개념: https://uxgjs.tistory.com/183
