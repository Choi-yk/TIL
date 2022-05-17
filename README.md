# TIL

> 오늘 배운 것을 기록합니다.

## git 특강 (220517~220518)
- CLI 기초
    - 터미널 명령어
        1. `touch`
        - 파일을 생성하는 명령어
        - 뛰어쓰기로 구분하여 여러 파일을 한꺼번에 생성 가능!

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

- Markdown
    - `.md` 확장자
    - 개발과 관련된 많은 문서가 마크다운 형식으로 작성됨
    - **각 역할에 맞는 문법을 사용해야 함!** 즉, 내가 쓰고싶은대로 쓰면 안됨

- Git 기초
    - Git 기본 명령어
        0. 로컬 저장소
        - `Working Directory (= Working Tree)`
        - `Staging Area (= Index)`
        - `Repository (commits)`

        1. git init
        - 현재 작업 중인 디렉토리를 Git으로 관리한다는 명령어
        - 터미널에는 `(master)`라고 표기됨. *이때, 이미 있다면 또 입력하면 안됨*

        2. git status
        - Working Directory와 Staging Area에 있는 파일의 현재 상태를 알려주는 명령어
        - 상태
            1. `Untracked` : Git이 관리하지 않는 파일 (한번도 Staging Area에 올라간 적 없는 파일)
            2. `Tracked` : Git이 관리하는 파일
            
        3. git add
        ```git add 파일/폴더 또는 .```
        - Working Directory에 있는 파일을 Staging Area로 올리는 명령어

        4. git commit
        ```git commit -m "커밋 메세지"```
        - Staging Area에 올라온 파일의 변경 사항을 하나의 버전(커밋)으로 저장하는 명령어
        - 각각의 커밋은 SHA-1 알고리즘에 의해 반환 된 고유의 해시 값을 가짐
        
        5. git log
        - 커밋의 내역을 조회하는 명령어
        - 옵션
            - `--oneline` : 한줄로 축약해서 보여줌