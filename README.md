# Git

- Git 은 파일의 버전을 관리하는 툴

## Git 설치

- https://git-scm.com
  ![Image](https://github.com/user-attachments/assets/5e34cfaf-148b-4d52-ae7b-3c5dfe9cfc47)
  ![Image](https://github.com/user-attachments/assets/7c939e9c-fca4-4d13-b4ac-e0514edc13ca)
  ![Image](https://github.com/user-attachments/assets/e4d619ca-d211-4022-bf16-0981d2a35d07)

![Image](https://github.com/user-attachments/assets/2cc11367-adb1-4928-9843-ad9d2557c580)
└ `반드시 VSCode 설치 후 진행하여야함 (목록 환인 필수)`

- 나머지는 기본값으로 설치 해주면 됨.

## Git 사용자 설정

- VSCode 에서 기본 터미널을 `Git Bash`로 설정함.
- 터미널 실행 단축키 : `Ctrl + ~`
- 세팅아이콘 선택 > Setting 메뉴 선택
  ![Image](https://github.com/user-attachments/assets/e36361b3-b533-48f2-8784-f000a6052f55)

- 검색란에 `Terminal default` 입력 > `Git Bash` 목록 선택
  ![Image](https://github.com/user-attachments/assets/b7f7b7fa-9903-4507-86fd-c572042bf81b)

## Git 정보 확인 및 세팅 (터미널에서 진행)

- Git 버전 확인

```bash
git --version
```

- 기본 브랜치명을 `main` 으로 설정하기 (초기 설치시 master로 되어있음)

```bash
git config --global init.defaultBranch main
```

-Enter 키를 통일시킴 (맥, 윈도우, 리눅스가 Enter키, 줄 변경이 달리 처리됨)

```bash
git config --global core.autocrlf true
```

- Git 수정내역, 즉 commit 시 메세지 상세 남기기 (VSCode 로 작성하도록 세팅)

```bash
git config --global core.editor "code --wait"
```

- 사용자 설정(아이디, 이메일 : 구글 계정과 GitHub 아이디 추천)

```bash
git config --global user.name "lynn.9702272"
git config --global user.email "lynn.9702272@gmail.com"
```

```
git config --global user.name
git config --global user.email
```

# GitHub

- 회원가입 (https://github.com) : 구글 계정으로 회원가입 추천
  例) til_git 저장소 생성 (생략)

## GitHub 사용자 계정 보안 설정

- 초기 설정시 다음 내용을 필수로 확인
  └ `자격 증명 관리자` > Windows 자격증명 관리 탭 > Git 관련 제거
  ![Image](https://github.com/user-attachments/assets/ab666a78-c86a-4131-8dd4-284c0fa1059b)
  ![Image](https://github.com/user-attachments/assets/76c2475d-ee3c-4d4f-8b0c-9cff1cb9eb1b)

- GitHub 자격증명 등록은 git push 진행되면 자동으로 로그인 팝업이 출력됨

## Git 작업 및 GitHub 연결 작업 진행

### 1. 최초 프로젝트 관리를 Git 으로 설정

```bash
git init
```

### 2. 현재 Git 프로젝트 상태

```bash
git status
```

### 3. Git 으로 파일 추적하기

```bash
git add README.md
```

### 4. Git 으로 모든 파일 추적하기

```bash
git add .
```

### 5. 작업 히스토리 남기기

- 간단하게 한줄로 메모 남기기

```bash
git commit -m "메세지"
git commit -m "깃허브 사용법 정리중"
```

- 여러줄 작업내역 남기기

```bash
git commit
```

### 6. commit 내역 컨벤션 알아보기

```
[commit type] commit message(option)

commit 상세내역
```

- commit type : 업무의 분류

```
[feat] 새로운 기능 추가함
[fix] 버그 수정
[docs] 문서 수정(README.md 등)
[style] 코드의 스타일(띄워쓰기, 세미콜론 등)
[refector] 코드 리팩토링(기능변경, 코드 정리 등)
[test] 테스트 코드를 추가 한 경우
[core] 기타(빌드 설정, 패키지 설정 등의 개발환경 변경 시)
```

- 옵션 : 23번 이슈를 해결했고, 회원가입 로그인 기능을 추가했다

```
[feat] 회원가입 로그인 기능 추가(#23)
```

### 7. commit 전체 내역 살펴보기

- 상세하게 살펴보기

```bash
git log
```

- 간략하게 보기

```bash
git log --oneline
```

- 하나의 commit 을 상세하게 보기 (End가 뜰때 종료 시 `q` 누르기)

git show commitID (lynn.9702272)

```bash
git show lynn.9702272
```

### 8. commit 내용 수정하기

- 바로 전 (직전) commit 내용 수정하기

```bash
git commit --amend
```

### 9. GitHub 의 온라인 주소 연결하기

_등록하기_

- git remote add 별명 주소

```bash
git remote add origin https://github.com/MOONYUBI/til_git.git
```

_목록보기_

```bash
git remote -v
```

- 삭제하기

git remote remove 별명

```bash
git remote remove aaa
git remote -v
```

### 10. GitHub로 등록(push)하기

- git push -u 별명 현재브랜치

```bash
git push -u origin main
```

git push // 위의 명령과 같음

### 11. 최소 알아야 하는 git 명령어

```bash
git add .
git commit
git push
```

# Git 으로 브랜치 관리하기

## Branch 란 ?

- 개발에서 구현해야 하는 각각의 기능이 있음.
- 하나의 기능을 구현 완료하였다면 소스를 버전으로 보관하는 것
- 다음 기능을 구현한다면 새로운 소스 버전을 만들어서 진행하는 것

## Branch 초기 이름 세팅

```bash
git config --global init.defaultBranch main
```

## Branch 생성하는 법

```bash
git branch 브랜치명
git branch trip
```

## Branch 목록 보는 법

```bash
git branch
```

## 원하는 Branch 로 이동하는 법

```bash
git switch 브랜치명
git switch trip
```

## 원하는 Branch 삭제하는 법

```bash
git branch -d 브랜치명

git branch      // ※목록 필수 확인※
git switch main // 다른 브랜치로 이동

git branch -d trip // 삭제 실습 (삭제 후 확인 必)
```

## 작업이 완료되면 Branch 합치기

```bash
git merge(합치다) 대상브랜치명
git merge trip
```

※새로운 브랜치를 git push 할 때 git push origin 브랜치명※

# Git commit 관리하기

## 1. 바로 이전 commit 내용 수정하기

- commit 실행 후 바로 내용을 수정하는 경우

```bash
git commit --amend (Enter키)

내용수정 진행 → 저장

git lod --oneline (Enter키)
```

## 2. 오래전 commit 내용 수정하기 (권장하지 않음 - 협업시 문제 발생할 수 있음.)

- commit history 알아보기

```bash
git log --oneline (Enter키)
```

例 )

```bash
$ git log --oneline
d1c3309 (HEAD -> main, origin/main) [docs] 브랜치의 이해
b69b523 [docs] 깃허브 기본 사용 및 연결법
189efb5 [docs] 깃허브 명령어를 공부하고 있음.
bd3256d [커밋타입] 커밋 타이틀
fea3e3b 깃허브 사용법 정리중
```

- 위 처럼 나온 곳에서 `pick bd3256d`을 `edit bd3256d` 으로 수정
- `pick`을 `edit` 으로 수정 후 저장

```bash
pick b69b523 [docs] 깃허브 기본 사용 및 연결법
pick 189efb5 [docs] 깃허브 명령어를 공부하고 있음.
edit bd3256d [커밋타입] 커밋 타이틀
```

- 해시값 파악 후 실행 (^ 기호는 시작이라는 뜻)

```bash
git rebase -i 해시값^ (Enter키)
```

例 )

```bash
git rebase -i bd3256d^
```

예제)

```bash
pick bd3256d [커밋타입] 커밋 타이틀
pick 189efb5 [docs] 깃허브 명령어를 공부하고 있음.
pick b69b523 [docs] 깃허브 기본 사용 및 연결법
pick d1c3309 [docs] 브랜치의 이해
pick 8459f84 진행중
```

- 위처럼 나온 곳에서 `pick b69b523` 을 `eidt b69b523` 으로 수정
- `pick`을 `edit`으로 수정 후 저장

예제)

```bash
pick bd3256d [커밋타입] 커밋 타이틀
pick 189efb5 [docs] 깃허브 명령어를 공부하고 있음.
pick b69b523 [docs] 깃허브 기본 사용 및 연결법
edit d1c3309 [docs] 브랜치의 이해
pick 8459f84 진행중
```

## 3. GitHub에 commit 수정 내용 반영하기

### 3.1 바로 수정 commit 수정 후 바로 push 하기

### 3.1 이전 commit 수정 후 바로 push 하기
