## GitHub로 협업하는 방법
#### [Part.1] 리더  
1. git bash 접속 후 `cd ~`를 통해 홈으로 간다.
2. `mkdir new_file` : 새로운 파일을 만든다.
3. `code .` : 새로 만든 파일이 있는 현재 프로젝트를 오픈한다. (Visual Stuido Code를 통해 열림)  
4. 프로젝트 작성 후 저장한다. (Ctrl+S)  
5. `git init` : git bash로 돌아와서 git init을 통해 git 폴더를 생성한다.  
6. `git add README.md` : README라는 마크다운에 작성한 사항을 더한다. (변경사항을 스테이징하는 단계)  
7. `git commit -m "First commit"`   
: git add로 스테이지에 올린 파일을 commit한다.  
: 첫번째 commit은 주로 "First commit" 메세지를 사용한다.  
8. `git log --oneline`을 통해 commit이 제대로 되었는지 한 줄로 확인한다.  
9. `git remote add origin [주소]` : 로컬에 있는 new_file을 원격 저장소에 올리기 위해 사용하는 명령어이다.    
10. `git remote -v`를 통해 제대로 remote되었는지를 확인한다.  
11. `git push origin main/master` : repository로 파일을 push한다.  

<br><br>  

#### [Part.2] 팀원  
1. `git clone [주소]` : 리더가 올린 파일을 clone을 통해 가져온다.  
2. `cd new_file` : git bash를 통해 홈에서부터 new_file로 이동한다.  
3. `git code .`를 통해 해당 파일을 visual studio code로 open한다.  
4. 리더가 작성한 프로젝트를 수정 및 추가 작성한다.  
5. `git add README.md` : 리더와 마찬가지로 변경사항을 스테이징한다.  
6. `git commit -m "메세지"` : 스테이징된 변경사항을 commit한다.  
- 참고) 리더가 이미 remote를 했기 때문에 팀원은 수정 작업 후 remote를 할 필요가 없다.  
7. `git push origin main/master`를 통해 repository로 파일을 push해야하는데...  

    - if, Error가 나온다면? go to [Part.2-2] 
           
    
<br><br>  

#### [Part.2-2] 프로젝트 push 권한 부여  
1. GitHub에 있는 해당 repository 내 settings을 클릭한다.  
2. Collaborators 내 add people을 통해 권한을 주고자 하는 작업자를 추가한다.  
3. 추가받은 작업자는 해당 reposiroty 내 invitation을 수락한다.  
4. 권한을 받은 작업자는 다시 git bash에서 `git push origin main/master`을 입력하면 오류없이 업로드가 가능해진다.  

<br><br>  

#### [Part.2-3] 리더의 권한 없이 pull request  
- 같은 팀 리더가 아닌 제 3자이거나 권한을 받기 어려운 경우, pull request를 통해 역으로 편집 제안을 할 수 있다.  
1. GitHub 내 repository 우측에 Fork를 클릭한다.  
2. Fork는 남의 repository를 나의 것처럼 복제하는 기능이다.  
3. Fork를 통해 복제하면 곧바로 GitHub에서 편집이 가능하다. 
4. 편집 후에는 원 작성자에게 create pull request를 통해 편집 제안을 해야한다.  
5. 원 작성자가 타인의 pull request를 보고 자신의 것과 merge하면 기존의 repository에 병합된다.   

<br><br> 

#### [Part.3] 이후 수정 작업
1. `git pull origin main/master`를 통해 프로젝트를 나의 컴퓨터로 pull한다.   
2. 수정 작업 후 똑같이 `git add -> git commit -> git push`를 통해 업로드한다.   


