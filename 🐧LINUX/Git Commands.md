## The 3 main parts of git
- working directory
- staging area(index)
- .git directory(repository)

## Git commands
- git help [command name]: 매뉴얼

- git init 
    + 현재 디렉토리를 working directory로 인식
    + 현재 디렉토리 안에 .git repository 생성

- git config user.name
- git config user.email
- git config alias.[alias] 'original command': 커맨드 별칭 설정 

git add: Add to Staging area
- git add [file name]
- git add [directory name]
- git add . 

git reset 
- reset staging
    + git reset [file name]: staging area에서 해당 파일 제거
- reset commit
    + git reset --soft [commit id]: head가 해당 커밋을 가리키도록 변경
    + git rest --mixed [commit id]: head가 해당 커밋을 가리키도록, staging area를 해당 커밋 시 상태로 초기화
    + git rest --hard [commit id]: head가 해당 커밋을 가리킫록, staging area를 해당 커밋 시 상태로 초기화, working directory를 해당 커밋 시 상태로 변경
        * [commit id] 대신에 HEAD^, HEAD~2 사용 가능

## 여러 커밋을 하나로 만들기
1, 2, 3, ,4, 5 커밋이 있고  HEAD는 5를 보고 있는 상황에서 2, 3, 4를 지우고 싶을 때.
1. git reset --soft 1 또는 git reset --mixed 1 해서 working directory는 그대로 둔 채 HEAD를 1로 옮긴다.
2. git add . 
3. git commit
    => 1, 5의 커밋 이력만 남는다.

- git status: 상태 조회

- git commit: 커밋. 커밋 메세지 입력 vim으로 연결됨 
- git commit -m "commit message": 커밋
- git commit --amend: 최신 커밋을 수정해 덮어쓰기


- git log: commit history
- git log --pretty=oneline: commit history 한 줄로 표시
    + git log --oneline 으로 짧게 사용도 가능
- git log --graph: commit hisotry 그래프와 함께 표시
- git log --all: 현재 브랜치가 아니라 ref/ 안에 있는 브랜치, 태그들의 커밋 표시

- git show [commit id]: commit 상세 정보
- git show [tag name]: tag 상세 정보 

- git diff [commit id A] [commit id B]: 두 커밋 차이 비교

- git tag: 전체 태그 목록 조회
- git tag [tag name] [commit id]: 특정 커밋에 태그 설정
- git show [tag name]: 특정 태그 정보 표시


reset vs checkout
- git reset [commit id]: 커밋되지 않은 변경사항 버리거나 커밋 폐기
- git reset [file name]: 해당 파일 staging 취소
- git checkout [commit id]: 해당 커밋으로 head 이동
- git checkout [branch name]: 브랜치 전환
- git checkout [file name]: working directory에서 수정한 내용 취소(복구 불가)

- git branch [branch name]: 새 브랜치 생성
- git branch -d [branch name]: 해당 브랜치 삭제
- git checkout [branch name]: 해당 브랜치로 이동
- git checkout -b [branch name]: 해당 이름의 새로운 브랜치를 만들고 이동
- git merge [branch name]: 현재 브랜치에 해당 브랜치 머지
- git merge --abort: conflict 발생 시 현재 머지 취소
    + merge
        * fast-forward
        * 3-way merge    
- git rebase [branch name]: 해당 브랜치로 현재 브랜치의 베이스 이동
    + 해당 브랜치에 현재 브랜치를 덮어씌우는 격
    + merge와 결과는 같지만 새로운 커밋을 만들지 않고 커밋 히스토리가 단순해짐

- git fetch: remote repository 내려받기
- git pull: fetch + merge
- git fetch => git diff => git merge
- git blame [file name]: 해당 파일 커밋 작성자 등 정보 표시
- git revert [commit id]: remote repo에 이미 push된 경우, 특정 commit과 일치하는 새로운 커밋 생성. revert 한 후 push 하면 해당 commit으로 덮어쓰기.
- git revert [commit id a]..[commit id b]: 복수의 commit을 revert. a는 포함, b는 미포함 돼 a는 돌아갈 지점이 됨.

- git reflog: reference log. HEAD가 가리켰던 지점들의 목록 표시

- git stash: 커밋하지 않은 working directory 내용을 스택에 임시 저장하고 working directory는 최신 커밋 기준으로 초기화
- git stash list: stash 목록 표시
- git stash apply [stash id]: stash 데이터를 working directory에 반영
- git stash drop [stash id]: stash 삭제
- git stash pop [stash id]: stash 데이터 반영 후 삭제
    + apply, drop, pop 모두 [stash id] 생략 시 최신 데이터 지칭

- @{u}, @{upstream}은 해당 브랜치의 upstream 브랜치를 가리킴
- git log @{u}.. : outgoing commits. local에는 있지만 upstream에 없는 커밋 표시
- git log ..@{u} : incoming commits. upstream에는 있지만 local에 없는 커밋 표시

- git cherry-pick [commit id]: 특정 커밋만 골라서 merge



