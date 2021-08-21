	- fix: bug-fix
	- refactor: refactoring
	
- License
    - MIT License: MIT에서 만든 라이센스로, 모든 행동에 제약이 없으며, 저작권자는 소프트웨어와 관련한 책임에서 자유롭습니다.
    - Apache License 2.0: Apache 재단이 만든 라이센스로, 특허권 관련 내용이 포함되어 있습니다.
    - GNU General Public License v3.0: 가장 많이 알려져있으며, 의무사항(해당 라이센스가 적용된 소스코드 사용시 GPL을 따라야 함)이 존재합니다.


- start project with git clone

- Branch
	- 똑같은 차원의 세계. 메타버스 : 분기점을 생성하여 독립적으로 코드를 변경할 수 있도록 도와주는 모델
	- git branch : 무엇이 브랜치인지 알려줌
	- git checkout(switch) stem
		- stem이란 브랜치 생성하고, 다른 코드를 생성 가능
	- git push origin stem
	- branch 병합: 주(main)에서 부를 땡김
		- git merge stem: stem 것을 main 것으로 병합
		- 기존의 main것은 롤백 가능. 방법은 나중에
	- branch 지우기: git branch -D stem
	- Conflict branch
		- git branch c-test
		- git merge c-test
			- 한 쪽 브랜치를 완전히 소거 : main 것을 제거 or 다른 브랜치를 제거bran
			- 둘을 적절히 조합


## 내일 할 일
- logical thinking TIL 작성 완료
- PRACTICE(1) -> 필수
- FINAL PRACTICE -> 선택



### Basic source code

Lyon Kim@Lyon MINGW64 ~/Documents/dev
$ git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager-core
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master

Lyon Kim@Lyon MINGW64 ~/Documents/dev
$ git config --global user.name "azureguy7"

Lyon Kim@Lyon MINGW64 ~/Documents/dev
$ git config --global user.email "azureguy7@gmail.com"

Lyon Kim@Lyon MINGW64 ~/Documents/dev
$ git config --global core.editor "vim"

Lyon Kim@Lyon MINGW64 ~/Documents/dev
$ git config --global core.pager "cat"

Lyon Kim@Lyon MINGW64 ~/Documents/dev
$ git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager-core
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.name=azureguy7
user.email=azureguy7@gmail.com
core.editor=vim
core.pager=cat

Lyon Kim@Lyon MINGW64 ~/Documents/dev
$ mkdir first-repo

Lyon Kim@Lyon MINGW64 ~/Documents/dev
$ ls
bin/  first-repo/  red.txt  write.txt

Lyon Kim@Lyon MINGW64 ~/Documents/dev
$ cd first-repo/

Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo
$ ls

Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo
$ git init
Initialized empty Git repository in C:/Users/Lyon Kim/Documents/dev/first-repo/.git/

Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo (master)
$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)

Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo (master)
$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)

Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo (master)
$ cd ..

Lyon Kim@Lyon MINGW64 ~/Documents/dev
$ git status
fatal: not a git repository (or any of the parent directories): .git

Lyon Kim@Lyon MINGW64 ~/Documents/dev
$ cd first-repo/

Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo (master)
$ git branch -M main

Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo (main)
$ git status
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)

Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo (main)
$ git remote

Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo (main)
$ git remote add origin https://github.com/azureguy7/first-repo.git

Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo (main)
$ git remote
origin

Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo (main)
$ git remote -v
origin  https://github.com/azureguy7/first-repo.git (fetch)
origin  https://github.com/azureguy7/first-repo.git (push)

Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo (main)
$


Token : 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

