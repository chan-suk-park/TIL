# git
분산 버전 관리 시스템
## git 영역
- working Directory

     실제 작업 중인 파일들이 위치한 영역
    
- staging Area

    작업 영역에서 변경된 파일 중 다음 버전에 포함시킬 파일들을 선택적으로 추가하거나 제외할 수 있는 중간 영역

- Repository

    버전(commit) 이력과 파일들이 영구적으로 저장되는 영역 모든 버전과 변경 이력이 기록됨

## git 주요 명령어 및 문법
- ```git init``` : 로컬 저장소 설정

- ```git add '파일 이름 or .(디렉토리 안 전체)```' : 작업 영역에서 staging area로 이동

- ```git commit -m '버전이름'``` : staging Area에서 repository로 이동


- ```git config --global user.email "주소"``` : 이메일 주소 설정(github 이메일)

- ```git config --global user.name "유저네임"``` : 유저 닉네임 설정(github 유저네임)

- ```git status``` : 현재 로컬 저장소의 파일 상태 보기

- ```git log``` : commit 목록 보기 (주소 포함)

- ```git log --oneline``` : commit 목록 한줄로 보기

- ```git config --list``` : 모든 설정 확인


❗ ```git init``` 후 내부파일에 다시 ```git init``` 선언 ❌

- ```git commit --amend``` 
    - Vim 에디터 오픈 후 직전 commit 수정 가능, Vim 나올 때는 ```:wq```(저장 후 나옴) 
    - 파일을 깜빡하고 안 넣은 경우에는 해당 파일을 staging area로 올리고 수정
- ```git remot add origin 'url'``` : 로컬 저장소에 원격 저장소 추가

- ```git push origin master``` : 원격 저장소에 commit 목록을 업로드

- ```git pull origin master``` : 원격 저장소의 변경사항만을 받아옴 (이미 파일이 존재하는 경우에 사용)

- ```git clone 'url'``` : 원격 저장소 전체를 복제 (이미 파일이 없는 경우에 사용, ```git init```을 하지않아도 자동으로 설정 되어있음)

- gitignore : git에서 특정 파일이나 디렉토리를 추적하지 않도록 설정하는 데 사용하는 텍스트 파일
    ```.gitignore 파일 생성 후 내부에 추적하지 않을 파일이나 디렉토리 작성```
    
    주의사항 : ```git init```전에 할 것

## git 기타 명령어
- ```git remote -v``` : 현재 로컬 저장소에 등록된 원격 저장소 목록 보기

- ```git remote rm '원격 저장소 이름'``` : 현재 로컬 저장소에 들록된 원격 저장소 삭제

## git revert, remove
- ```git revert<commit id>```
  |commit|변경사항|
  |------|------|
  |first| 1번 파일 추가|
  |second| 2번 파일 추가|
  |third| 3번 파일 추가|
   
  
  ```git revert "second log값 4자리"```
  하는 경우 vim 편집기가 실행되고 second를 없던 일로 만들고 그 행위를 새로운 commit으로 기록
  
  (이 경우 2번 파일은 삭제되지만 second commit은 삭제되지 않고 그대로 남아 있음)
  