# git & github

## 주제: git과 github

## 키워드

- init, add, commit
- branch와 merge
- pull, push
- git flow


git : 버전 관리 소프트웨어 (작업한 코드들 기록, 보관)

**git init** : git이라는 소프트웨어가 작업 폴더 감시 시작

**git add 파일 명** : 파일 현재 상태를 기록 

**git commit -m ‘메시지’** : 메모 

![작업 폴더 안의 여러 파일들 중 내가 기록을 남기고 싶은 파일을 고르는 것 (git add) → git commit 명령어를 이용해서 기록 저장소(repository)로 옮기는 것](git%20&%20github%20a12c58cf7d02424794f237cab00f34a5/%25EC%258A%25A4%25ED%2581%25AC%25EB%25A6%25B0%25EC%2583%25B7(76).png)

작업 폴더 안의 여러 파일들 중 내가 기록을 남기고 싶은 파일을 고르는 것 (git add) → git commit 명령어를 이용해서 기록 저장소(repository)로 옮기는 것

- *staging area* : commit 하기 전에 commit할 파일들을 골라 놓는 곳
- *repository* : commit된 파일의 버전들을 모아 놓은 곳

---

**git branch 브랜치명** : 브랜치 생성 (사본)

**git switch 브랜치명** : 브랜치 이동

![스크린샷(83).png](git%20&%20github%20a12c58cf7d02424794f237cab00f34a5/%25EC%258A%25A4%25ED%2581%25AC%25EB%25A6%25B0%25EC%2583%25B7(83).png)

- 복사본 브랜치(ex. coupon branch) 를 main 브랜치에 합치고 싶을 때
    1. git switch main : 기준이 되는 브랜치로 이동
    2. **git merge** coupon 
    
    >coupon과 main 브랜치가 각각 다른 것을 개발 했을 때 : 성공적으로 merge
    
- **merge**
    - **3-way merge** : 각 브랜치에 신규 commit이 있는 경우 (위의 방식)
    - **fast-forward merge :** main 브랜치에 신규 commit이 없는 경우 git merge —no-ff 브랜치명 ⇒ 강제로 *3-way-merge* 발생 시킴
    - **git rebase&merge :** 신규 브랜치의 시작점을 마음대로 다른 커밋으로 옮길 수 있음 (rebase) > 브랜치의 시작점을 최근 커밋으로 옮긴 후 *fast-forward merge* 하는 방식
    - **squash and merge :** 신규 브랜치의 커밋들 모두 합쳐 하나의 커밋으로 메인 브랜치에 더해줌

---

**git push** : 현재 작업 폴더에 있는 로컬저장소를 원격 저장소로 업로드

(**git push -u 원격저장소주소 올릴로컬브랜치명)**

→ *보통 git push 전에 git pull 먼저 해야함*

**git pull 원격저장소주소 브랜치명** 

: 원격 저장소의 내용을 가져와서 로컬 저장소와 합쳐줌

최신 원격 저장소의 변동 내용이 로컬 저장소에 반영됨 > 이 경우에만 git push 가능

---

- **git flow** : 크게 5개의 브랜치 운영
    - main 브랜치
    - develop 브랜치 (개발용)
    - feature 브랜치 (develop에 기능추가용)
    - hotfix 브랜치 (main 브랜치 버그해결용)
    - 가끔 release 브랜치 (develop 브랜치를 main 브랜치에 합치기 전에 최종 테스트용)
