## Git
- (버전을 통해, 분산된 방식으로) 코드를 관리하는 도구    
- 코드관리?   
    - 백업도구  
    - 협업도구  
    - 배포도구  
<br>  

- SCM(Source Code Management) : 코드 관리 도구로써의 Git을 의미  
- VCS(Version Control System) : 버전 관리 시스템(도구)로써의 Git을 의미  
- DVCS(Distributed VCS) : 분산형 버전 관리 시스템(도구)로써의 Git을 의미   

<br/><br/>       
         

## Git 명령어  
### [part.1 버전 관리 Git 명령어] 
[1] &nbsp; `git init`:  &nbsp; Git 프로젝트를 시작한다는 의미의 명령어  
- Git은 폴더/디렉토리 단위로 코드를 관리한다.  
- So, Git 프로젝트 시작 전에는 해당 프로젝트를 관리할 폴더/디렉토리를 생성해야 한다.  
- 결과 : 프로젝트 폴너 내에 `.git` 폴더 생성   

<br/>

```
$ git init 
Initialized empt Git respository in C:/Users/skqk3/test/.git/ 
```  
(.git? 점은 숨김파일을 의미! 즉, test파일 안에 숨김파일로 git파일이 만들어진것임 
)  

<br/>

[2]  &nbsp; `git status` :  &nbsp; Git 상태 출력  
- 결과 

<br/>

(최초 상태)
```
On branch master -> master라는 branch에 있음

No commits yet -> commit이 아직 없음

nothing to commit (create/copy files and use "git add" to track) -> commit할 것도 없음
```    

<br/>

(`a.txt` 파일 생성 후 상태)  
```
On branch master

No commits yet

Untracked files: -> 추적되지 않은 파일 있음 
  (use "git add <file>..." to include in what will be committed)
        a.txt
   -> 어떻게 할지 팁을 알려줌(츤데레)
   -> commit 될 것에 포함시키고 시키면 git add <파일명>을 사용해 

nothing added to commit but untracked files present (use "git add" to track)
 -> commit 할 것은 없는데, 추적되지 않은 파일은 있어 (추적하고 싶으면 git add 사용해) 
```   

<br/>

(`git add a.txt` 입력 후 상태)
```
On branch master

No commits yet

Changes to be committed: 
  (use "git rm --cached <file>..." to unstage)  -> 내일 배우는 내용
        new file:   a.txt
```   

<br/>

(`git commit` 실행 후)
```
On branch master
nothing to commit, working tree clean
-> commit 할게 없음, working tree(== working directory, 작업중인 폴더)가 깔끔하다. 
```      

<br/>

(`git add b.txt` 후) 
```
Your branch is up to date with 'origin/master'.  
-> 너의 branch는 origin/master와 동기화되었다.  

Untracked files:  
  (use "git add <file>..." to include in what will be committed)
      b.txt  

nothing added to commit but untracked files present (use "git add" to track)
``` 
<br><br>

[3] &nbsp;  `git add [파일/폴더]` :  &nbsp; commmit을 하기 위한 (== 버전을 생성하기 위한 준비단계)  

<br/><br/>

[4] &nbsp;  `git commit -m "메시지"`  
- commit : 버전을 생성하는 역할  
- 보통 처음꺼는 git commit -m "First commit" or "Initial commit"을 사용  

<br/>

(최초 commit 시)
```
Author identity unknown -> 작자 미상
 
*** Please tell me who you are. -> 너가 누군지 알려줘  

Run -> 실행해봐

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity. -> 너의 계정의 기본 신원을 설정하기 위해
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'skqk3@LAPTOP-4602OEH2.(none)')
```  
  
<br/><br/>

  [5]  &nbsp; `git config` : &nbsp;  Git 관련 설정 (최초 한번만 설정하면 됨)  
  ```
    git config --global user.email "you@example.com" 
  git config --global user.name "Your Name"
  ```
    
      
- 참고) `cat ~/.gitconfig` 명령어 입력하면 내가 설정한 email과 name이 나온다.  

<br/><br/>

[6] &nbsp; `git log` : &nbsp;  Commit 목록을 불러옴  
- commit이 잘됐는지 확인할 때 사용하는 명령어  

<br/><br/>

### [Part.2 백업 Git 명령어]  
 
[7] &nbsp;  `git remote` :  &nbsp; 원격 저장소  
- 원격 저장소(Remote Repository)에 대한 정보 
- `git remote add` : 원격 저장소 추가  
- `git remote add [저장소이름] [저장소주소]`  
- `git remote add origin https://github.com/xxx` : 첫번째 저장소는 origin 칭호가 붙음  
     
<br/><br/>

[8]  &nbsp; `git push` :  &nbsp; 원격 저장소에 프로젝트 업로드  
- `git push [저장소이름] [브랜치이름]`  
- `git push origin master`  

<br><br>  

[9]  &nbsp; `git clone` :  &nbsp; 원격 저장소 프로젝트 다운로드  
- `git clone [저장소주소]` : 이렇게 가져오면 폴더명은 Github 내 원격 저장소 이름(remote-test)으로 가져옴  
- `git clone [저장소주소] [경로/폴더이름]` : 이렇게 하면 가져온 폴더 이름을 내가 지정(test) 할 수 있음   

