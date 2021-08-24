#20210824 TIL

# github pages를 이용한 github blog 만들기
- config.yml을 설정
- source/_posts 안에 md 파일 생성
- `hexo clean && hexo generate
- `hexo server
 : local에서 확인하고
- `hexo clean && hexo deploy


##branching models
- Branch 전략: git flow

### git flow
- 브랜치를 활용해서 버전 관리를 하는 것
 - 사용자가 보게 될 최종 상태의 파일만 존재하는 곳이 main branch
 - 디폴트 작업 공간은 develop 
 - 특정 기능에 대해서 feature로 따서 작업하고, 이후에 버전업, 올리자고 하면 develop으로 모으고 main으로

### Hotfix
- 긴급 보안 업데이트가 일례
- main에 있는 것을 바로 수정해서 반영하는 것

### release
- main과 develop 브랜치에 모두 merge

#### Summary of actions:
- Release branch 'release/v0.1' has been merged into 'main'
- The release was tagged 'v0.1'
- Release tag 'v0.1' has been back-merged into 'develop'
- Release branch 'release/v0.1' has been locally deleted
- You are now on branch 'develop'

# Revert Everything!!!
- 이름 변경 후 다시 원이름으로 mv하면 되돌려짐. 
	- commit할게 없음
- git checkout -- A
	- undoing: 최신 commit으로부터 되돌리기
- git checkout -- .
	- 모든 파일 되돌리기
- push를 하기 전까지는 모든 것 되돌리기 가능. but push 이후에는 아주 힘듦
- reset은 절대 사용 금지. 
	- git revert --no-commit HEAD~3..
		- .. 필수

# github issue와 projects 사용하기

# 협업 하는 법: Forking Workflow
-3조: https://github.com/seungjaepack/cowork-practice.git
https://github.com/seungjaepack/cowork-practice2.git

## [팀장]
- 팀장이 Repo 만들기: cowork-practice
- $ git clone 주소
- 작업 폴더에서 develop 브랜치 생성: $ git flow init
- 파일 두 개 생성
	- touch introduce.md 그리고 touch fizzbuzz.py
	- 둘 다 feat 라서 동시 commit
- develop push: $ git push -u origin develop
- 팀원들에게 github에 올렸다고 알려줌.
- issue 만들기
	- issue는 만든 사람만이 체크를 할 수 있음.
	- 따라서, 팀원들이 셀프 체크하게 하려면 팀원들이 만들게 해야 함.
- Fork: 해당 레포를 팀원들에게 갈라주는 것

- issue와 project 관리하기
	- Assignees, Labels, Milestone
	- Scrum board 생성 in PJT
- Pull Request 관리

## [팀원]
- Dev 폴더 이동
$ cd Documents/dev/

- 팀장이 fork해준 내 레포 주소 clone
$ git clone https://github.com/azureguy7/cowork-practice2.git

- 폴더 이동
$ cd cowork-practice2/

- Lyon Kim@Lyon MINGW64 ~/Documents/dev/cowork-practice2 (main)
$ git flow init

- remote 상태 확인
$ git remote -v
origin  https://github.com/azureguy7/cowork-practice2.git (fetch)
origin  https://github.com/azureguy7/cowork-practice2.git (push)

- 팀장 upstream 주소 추가
$ git remote add upstream https://github.com/seungjaepack/cowork-practice2.git

- remote 재확인
$ git remote -v
origin  https://github.com/azureguy7/cowork-practice2.git (fetch)
origin  https://github.com/azureguy7/cowork-practice2.git (push)
upstream        https://github.com/seungjaepack/cowork-practice2.git (fetch)
upstream        https://github.com/seungjaepack/cowork-practice2.git (push)

- 작업 feature 생성
Lyon Kim@Lyon MINGW64 ~/Documents/dev/cowork-practice2 (develop)
$ git flow feature start fb

- 파일 작업(생성/수정 > add > commit)
	* 마지막 commit에서 'resolve/fix/close' 표시
	** 'resolve #1' 과 같은 형태로 입력

- feature 종료
$ git flow feature finish fb

- 내 develop 브랜치에 올리기
$ git push -u origin develop

- pull request 하기

## sync 맞추기
[팀원]
git fetch upstream develop: 팀원이 팀장거를
git merge FETCH_HEAD: 

[팀장]
git pull origin develop



--------------------------------------
for i in range(1,16+1):
    if i%3==0:
        print('fizz')
    elif i%5==0:
        print('buzz')
    else:
        print(i)

for i in range(1,16+1):
    if i%15==0:
        print('fizzbuzz')
    elif i%3==0:
        print('fizz')
    elif i%5==0:
        print('buzz')
    else:
        print(i)
		

for i in range(1,16+1):
	if i%3==0 or i%5==0:
		print('fizz'*(i%3==0) + 'buzz'*(i%5==0))
	else:
		print(i)
