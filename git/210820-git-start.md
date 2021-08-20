# 210820 TIL

## 오늘 한 일
- shell command
	- CLI : command line interface <> GUI: graphic user interface
	- 커널: 하드웨어와 소프트웨어 브릿지
	- 쉘: 커널과 유저 브릿지 i.e. 탐색기(GUI 기반)

	- ls : list segment
		- - : 뒤에 붙는 거. flag(옵션들)
			- -l : line by line
			- -a : 숨긴 녀석들까지 (all)
	- clear: 화면 삭제
	- cd .. : 위로
	- cd : 현재 위치 최상단으로. 언제든 cd 엔터면 돌아온다 (cd / : 시스템 OS 상단으로)
	- mkdir
	- touch : 텍스트기반 파일 만들기
	- mv, cp
	- rm : 파일만.
		- rm -rf 폴더: 모조리 지우는 명령이기 때문에 조심
		- 폴더는 경로의 의미이기 때문에 그 안의 것들을 지우고 지워야 함.
	- mv A B : 이름 변경
	
- vim command
	- vi A : A파일을 vi로 오픈. ~(틸드)만 존재. 이 파일의 끝입니다라는 의미.
		- 처음은 normal 모드
			- 명령어가 키 하나로
		- 편집은 insert 모드에서 'i' 클릭
			- normal 모드로 돌아가려면 escape
		- vimium 설치해서 연습 (화살표: hjkl)
		- shift y  줄 카피
		- y2j 밑으로 두줄 카피 ; y3j 밑으로 세줄 카피
		- u : undo <> ctrl r 이 다시 하기
		- p: paste
		- d: 삭제
			- dd: 현재 한 줄 삭제
			- d2j: 밑으로 두 줄 삭제
		- o : normal 라인에서 아래로 insert 열
			- shift o: 위로 insert 오픈
		- a : 바로 수정 (append)

- markdown syntax
	- html보다 훨씬 간단하게 사용 가능하다

	# Markdown
	## Heading 2
	### Heading 3
	#### Heading 4
	##### Heading 5
	###### Heading 6  가장 작은 폰트

	Hyper Text Markup Language

	Markdown

	<a href="/"> Go to home</a>

	[Go to home](/)

	어떤 문단을 표현하고 싶다면 기호없이 문장을 연달아 입력하면 된다. 두번째 문장도 그냥 적으면 된다.

	문단 구분이 필요하다면 Enter키를 두 번 눌러준다.
	그렇지 않으면 한 문단으로 표현된다.

	## Covid-19 vaccine list

	- pfizer
	- moderna
	- jansen
	- astrazeneka

	## 건강관리를 위해 해야할 일의 순서

	1. 집에 오자마자 손을 씻는다.
	2. 손을 씻고 외부 물품을 정리한다.
	3. 정리 후, 다시 손을 씻는다.


	## Links and images

	[Go to google](https://www.google.com)

	[Go to home](/)

	[Go to top](#top)

	![A man is sitting on the chair.](download.jpg)


	## Code block

	To install this project, try `$ pip install -r requirements.txt`.

	To highlight some `word`, use backquote.

	```python
	import random

	result =[]
	for _ in range(6):
		num = random.randint(1,45)
		result.append(num)

	print(result)
	```

	:wq 저장 후 나가기
	
- git config
	- $ git config --global user.name "{github username}"
    - $ git config --global user.email "{github email address}"
    - $ git config --global core.editor "vim"
    - $ git config --global core.pager "cat"
    - $ git config --list
	
- start project with git init
    - Lyon Kim@Lyon MINGW64 ~/Documents/dev/first-repo
    - $ git init
	- $ git branch -M main
	- $ git remote add origin https://github.com/azureguy7/first-repo.git
	- $ git remote -v : 확인

- add > commit > push
	- add: blob을 working directory에서 stage로 이관
	- commit: stage의 blob에 대해 metadata작성 및 snapshot
	- push: local repo에 적재된commit들을 remote repository로 이송
	
    - $ mkdir first-repo && cd first-repo
    - $ git init
    - $ git remote add origin https://github.com/{username}/{reponame}.git
    - $ touch README.md
    - $ git add README.md
    - $ git commit -m "docs: Create README.md"
    - $ git push -u origin master 
		- -u는 생략가능
		- $ git branch -M main : master는 main으로 변경됨

- Commit Convention: 50자 이내, 제목과 내용사이 한 칸, prefix 사용
	- feat: features
	- docs: documentations
	- conf: configurations
	- test: test
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