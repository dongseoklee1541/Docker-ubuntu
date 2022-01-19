# git 개념

working tree : 버전으로 만들어지기 전 단계, 파일을 수정하는 곳

Staging Area : 버전을 만들려고 하는 파일들, 수정한 파일들을 모두 버전으로 만들지 않을때 버전으로 만들기 위한 파일들만 선정한 공간

Repository : 버전이 저장 되있는 곳 , ex) .git

commit : version

HEAD : 현재 가리키고 있는 버전

# git 명령어

`git init` : Initialize repository

`.git` : git repository

`git status` :  working tree status 
  *  modified : 기존에 Staging 또는 버전에 저장이 되있는 파일
  *  new file : 처음으로 Staging Area에 올라온 파일

`git add` : add to staging area , 버전으로 만들 파일을 working tree에서 staging Area 로 이동

`git commit` : create version + `-m "Msg"` ( 커밋과 동시에 설명 남기기) , staging Area에서 Repository로 이동

`git log` : show version

  * `git log --stat` : commit된 파일들의 history 를 보여줌
  * `git log -p` : 버전과 버전 사이의 차이점을 비교

`git diff` : Show changes, 마지막 버전과의 차이점을 보여준다

`git checkout 'name'` : HEAD를 'name'의 버전으로 돌린다.
  * `git checkout master` : HEAD를 최신 버전(master)로 돌린다.
