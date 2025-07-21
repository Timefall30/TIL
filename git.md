# Git

## 분산 버전 관리 시스템



- 코드의 버전(히스토리) 관리

- 개발되어 온 과정 파악

- 이전 버전과의 변경 사항 비교, 협업 도움



## git의 3가지 영역

- Working Directory : 실제 작업 중인 파일들이 위치하는 영역

- Staging Area : Working Directory에서 변경된 파일 중, 다음 버전에 포함시킬 파일들을 선택적으로 추가하거나 제외할 수 있는 중간 준비 영역

- Repository : 버전 이력과 파일들이 영구적으로 저장되는 영역. 모든 버전과 변경 이력이 기록됨.

버전 = commit

## Commit

변경된 파일들을 저장하는 행위, snapshot이라고도 함



___

# git의 동작

1. git init : 로컬 저장소 설정(초기화) git의 버전 관리를 시작할 디렉토리에서 진행

2. git add : 변경사항이 있는 파일을 staging area에 추가

3. git commit : staging area에 있는 파일들을 저장소에 기록 : 해당 시점의 버전을 생성고 변경 이력을 남기는 것

4. git commit -m'commit 메세지'

5. git config --global user.email "tatanan4604si0@gmail.com"

6. git config --global user.name "서울1반_이시우"

7. git status : 현재 로컬 저장소의 파일 상태 보기

8. git log : commit history 보기

9. git log --oneline : commit 목록 한 줄로 보기

10. git config --global --list : git global 설정 정보 보기



## git init 주의사항

git 로컬 저장소 내에 또다른 git 로컬 저장소를 만들지 말 것

git 로컬 저장소인 디렉토리 내부 하단에서 git init 명령어를 다시 입력하지 말 것.

git 저장소 안에 git 저장소가 있을 경우 가장 바깥 쪽의 git 저장소가 안쪽의 git 저장소의 변경사항 추적 불가



## 바로 직전 생성한 commit 수정하기

## git commit --amend



- commit 메세지 수정
1. commit 목록에서 commit의 hash 값 확인

2. git commit --amend 입력

3. Vim 에디터가 열리면서 직전 commit 메세지 수정 가능

4. Vim 저장 후 종료, commit 메세지 수정 후 변경된 commit 메세지와 commit 해시 값 확인
- commit 전체 수정
1. staging area에 작업 추가

2. git commit --amend

3. vim 에디터가 열리면서 새로운 commit 정보를 확인 및 수정 가능

4. vim 저장 후 종료, commit 메세지 수정 후 변경된 commit 메시지와 commit 해시 값 확인

5. 


