# Remote Repository

# 원격 저장소

코드와 버전 관리 이력을 온라인 상의 특정 위치에 저장하여 여러 개발자가 협업하고 코드를 공유할 수 있는 저장 공간



## 로컬 & 원격 저장소

1. git hub 가입

2. 공용 문서 "GitHub 설정 변경하기 문서 진행"

3. GitHub repository 생성

## 로컬 저장소에 원격 저장소 추가

git remote add origin remote_repo_url

origin은 별칭으로 별칭을 사용해 로컬 저장소 한 개에 여러 원격 저장소를 추가 할 수 있음

remote_repo_url은 추가하는 원격 저장소의 url이다.



git remote -v로 등록된 원격 저장소 목록을 확인가능하다.



## git push origin master

원격 저장소에 commit 목록을 업로드

최초 push 시 github 인증서 필요



### git pull origin master

원격 저장소의 변경사항만을 받아옴 (업데이트)

### git clone remote_repo_url

원격 저장소 전체를 복제 (다운로드)

clone으로 받은 프로젝트는 이미 git init이 되어 있음

### gitignore

git에서 특정 파일이나 디렉토리를 추적하지 않도록 설정하는 데 사용되는 텍스트 파일

프로젝트에 따라 공유하지 않아야 하는 것들도 존재하기 때문

1. .gitignore 파일 생성 (파일명 앞에 '.' 입력, 확장자 없음)

2. gitignore에 무시할 파일 입력

3. git init

4. git status로 확인

### gitignore 주의사항

이미 git의 관리를 받은 이력이 있는 파일이나 디렉토리는 나중에 gitignore에 작성해도 적용되지 않음 (git rm --cached 명령어를 통해 git 캐시에서 삭제 필요)

gitignore 목록 생성 서비스

[toptal](https://www.toptal.com/developers/gitignore/)



### git의 기타 명령어

- git remote -v : 현재 로컬 저장소에 등록된 원격 저장소 목록 보기

- git remote rm 원격_저장소_이름 : 현재 로컬 저장소에 등록된 원격 저장소 삭제



## Git revert

특정 commit을 없었던 일로 만드는 작업

git revert <commit id>

"재설정"

단일 commit을 실행 취소 하는 것

프로젝트 기록에서 commit을 없었던 일로 처리 후 그 결과를 새로운 commit으로 추가함

변경 사항을 안전하게 실행 취소할 수 있도록 도와주는 순방향 실행 취소 작업

commit 기록에서 commit을 삭제하거나 분리하는 대신, 지정된 변경 사항을 반전시키는 새 commit을 생성

git에서 기록이 손실되는 것을 방지하며 기록의 무결성과 협업의 신뢰성을 높임

## revert 실습

1. commit 목록 확인, 해시값 확인

2. git revert 해시값4자리입력

3. vim 편집기 실행

4. vim 편집기 저장 후 종료

5. 기존 commit은 삭제되지 않고 새로운 commit이 작성됨



## revert 추가 명령어

- 공백을 사용해 여러 commit을 한꺼번에 실행 취소 가능

- '..'을 사용해 범위를 지정하여 여러 commit을 한꺼번에 실행 취소 가능

- commit 메세지 작성을 위한 편집기를 열지 않음 (자동으로 commit 진행)

- 자동으로 commit 하지 않고, Staging Area에만 올림(이후에 직접 commit 해야함)

- 이 옵션은 여러 commit을 revert 할 때 하나의 commit으로 묶는 것이 가능



# Git reset

특정 commit으로 되돌아가는 작업

git reset [옵션] <commit id>

"되돌리기", 시계를 마치 과거로 돌리는 듯한 행위

특정 commit으로 되돌아 갔을 때, 되돌아간 commit 이후의 commit은 모두 삭제됨



## reset의 3가지 옵션

## --soft, --mixed, --hard

삭제되는 commit들의 기록을 어떤 영역에 남겨둘 것인지 옵션을 활용해 조정할 수 있음.

- --soft : 삭제된 commit의 기록을 staging area에 남김

- --mixed : 삭제된 commit의 기록을 working directory에 남김 (기본 옵션 값)

- --hard : 삭제된 commit의 기록을 남기지 않음



## git reset 실습

1.  commit 목록 확인, 해시값 확인

2. git reset --soft 해시값4자리입력 이 커밋 이후 커밋은 삭제됨

3. git log --oneline

4. commit 목록 확인

### git reflog

reset의 --hard 옵션을 통해 지워진 commit도 reflog로 조회하여 복구 가능.

### git undoing

파일 내용을 수정 전으로 되돌리기

Staging area에 올라간 파일을 unstage 하기

### git restore

Modified 상태의 파일 되돌리기 

working directory에서 파일을 수정한 뒤, 파일의 수정 사항을 취소하고, 원래 모습대로 되돌리는 작업

git restore를 통해 수정 취소 후에는 해당 내용을 복원할 수 없음.

원래 파일로 덮어쓰는 원리이기에 수정한 내용은 전부 사라짐

### Unstage 하는 명령어

1. git rm --cached 
   
   staging area에서 working directory로 되돌리기 git 저장소에 commit이 없는 경우
   
   

2. git restore --staged
   
   Staging area에서 working directory로 되돌리기 git 저장소에 commit이 존재하는 경우
   
   


