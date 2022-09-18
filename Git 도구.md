#### 리비전 조회하기
git reflog : 브랜치와 HEAD가 가리키는 커밋 조회
git show 22b54cc: 커밋 ID에 대한 git 내용 출력
git 계통 관계를 config에 저장하기
```bash
[alias]
	logs =log 
             --color 
             --oneline 
             --all 
             --graph
             --pretty=format:
                 '%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) 
                 %C(bold blue)<%an>%Creset'
             --abbrev-commit
```
사용예:
```
git logs
```

#### Stashing
브랜치를 변경하여야 할 때 현재 작업중인 것을(working + staging) commit하지 않고 스택에 저장하도록 하는 기능
```
git statsh
```

stash 하기 전

```git
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    Ch3.  Git  브랜치.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Git 도구.md


```

stash 명령후

```git
PS C:\Users\kwanw\Desktop\work\GitStudy> git stash
Saved working directory and index state WIP on main: 051ba6f 제목 변경

PS C:\Users\kwanw\Desktop\work\GitStudy> git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Git 도구.md
```

저장한 stash 확인
```git
PS C:\Users\kwanw\Desktop\work\GitStudy> git stash list
stash@{0}: WIP on main: 051ba6f 제목 변경
```

stash 파일 복원하기 
```git
git stash apply --index
```

stash 제거하기
```git
git stash drop
git stash dropstash@{0}
```

stash 관련 명령어들
`git stash` : 추적중인 파일만 저장한다.
`git stash --keep-index` : stagin area 파일은 stash 하지 않는다
`git stash -u` : 추적중이지 않은 파일까지 포함하여 stash


