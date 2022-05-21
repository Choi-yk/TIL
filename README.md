# TIL

> 오늘 배운 것을 기록합니다.

## git 특강 (220517~220518)
### 1. CLI

#### 터미널 명령어

1. `touch`
   - 파일을 생성하는 명령어

2. `mkdir`

   - 새 폴더를 생성하는 명령어
   - 뛰어쓰기로 구분하여 여러 파일을 한꺼번에 생성 가능!


3. `ls`

   - list segments
     
   - `-a` : all 옵션. 숨김 파일까지 모두 보여줌
     
   - `-l` : long 옵션. 용량, 수정 날짜 등 파일 정보를 자세히 보여줌
4. `mv`
   
   - 폴더/파일을 다른 폴더 내로 이동하거나, 이름을 변경하는 명령어
5. `cd`

   - `cd ~` = `cd` : 홈 디렉토리로 이동
     
   - `cd ..` : 부모 디렉토리로 이동 (위로 가기)
     
   - `cd -` : 전 디렉토리로 이동 (뒤로 가기)
6. `rm`
   - 폴더/파일 지우는 명령어
   - GUI와 달리 휴지통으로 이동하지 않고, 완전 삭제함
   - `-r` : recursive 옵션. 폴더를 지울 때 사용함



### 2. Markdown
- `.md` 확장자
- 개발과 관련된 많은 문서가 마크다운 형식으로 작성됨
- **각 역할에 맞는 문법을 사용해야 함!** 즉, 내가 쓰고싶은대로 쓰면 안됨



### 3. Git 기초
#### git의 세 공간

- Working Directory (= Working Tree)
- Staging Area (= Index)
- Commits

#### git 명령어

```bash
## 로컬 저장소
git init # git으로 버전관리하는 레포지토리로 만들기
git add . # WD -> SA
git commit -m '변경 사유' # SA -> Commits
```

#### github

```bash
git remote add origin URL # 길 연결
git remote -v # 길 확인

git push origin master # origin 레포지토리의 master브랜치로 올려주기
```

#### Pull & Clone

- 로컬 저장소와 github 연결하기

```bash
git pull origin master # github -> local 변경사항 반영할 때
git clone URL # 한 번만 하기, URL로 복제 (주의: repository에서 clone하면 안됨)
```

- 충돌(Conflict) 해결하기

  - rejected 발생

    `pull` -> 편집 -> 저장 -> `add` -> `commit` -> `push`

- Branch

```bash
git branch # 브랜치 목록확 인
git branch 브랜치명 # 브랜치 신규 생성
git branch -d 브랜치 명 # 브랜치 삭제
git branch -D # 강제 삭제
git switch # HEAD 이동 (포인터)
git switch -c # 신규 생성 후, 이동
```

- Branch merge (병합)

```bash
git merge 브랜치 명 # master에서 하기
```

#### reset / revert

1. git reset

```bash
git reset [옵션] 커밋 ID
```
- 커밋 내역을 삭제
- 옵션
    - `--soft` 
      - Staging Area로 돌려놓음 (commit 하기 전 상태)
      - 다시 commit 할 수 있는 상태가 됨
    - `--mixed` (기본값) 
      - Working Directory로 돌려놓음 (add 하기 전 상태)
      - unstage 상태
    - `--hard`
      - 이후의 commit 된 파일들(`tracked` 파일들)은 모두 working directory에서 삭제함

2. git revert

```bash
git revert 커밋 ID
```

- 이전 커밋을 취소한다는 새로운 커밋을 만듦
