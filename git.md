# git 개념

working tree : 버전으로 만들어지기 전 단계, 파일을 수정하는 곳

Staging Area : 버전을 만들려고 하는 파일들, 수정한 파일들을 모두 버전으로 만들지 않을때 버전으로 만들기 위한 파일들만 선정한 공간

Repository : 버전이 저장 되있는 곳 , ex) .git

commit : version

# git 명령어

`git init` : Initialize repository

`.git` : git repository

`git status` :  working tree status 

`git add` : add to staging area , 버전으로 만들 파일을 working tree에서 staging Area 로 이동

`git commit` : create version + `-m "Msg"` ( 커밋과 동시에 설명 남기기) , staging Area에서 Repository로 이동

`git log` : show version
