## vim 을 사용하는 이유?
마우스 없이 모든걸 할 수 있는 편집기라는 장점


# vi Editor

* 명령(command) mode --> 편집 mode : 명령모드에서 i(insert, 끼워넣기) 또는 a(append, 뒤에 이어넣기) 를 눌러서 편집모드로 전환한다.

* 편집 모드 --> 명령 모드 : 편집모드에서 esc

<img src="https://github.com/dongseoklee1541/Docker/blob/master/image/99b983892094b5c6d2fc3736e15da7d1.png?raw=true">


### 방향 전환
h,j,k,l 로 방향을 이동할 수 있다. h는 좌 l은 우 j는 아래 마지막으로 k는 위다. 
* HML : 화면의 제일 위, 중간, 아래로 커서 이동
* w : 단어 단위로 이동
  * $(Shift+4) : End Key
  * ^(Shift+6) : Home Key
* ctrl + f or u or b : f는 페이지 다운, u 또는 b는 페이지 업이다.

### 수정
* `x` : 한칸 지우기
* X(shift + x) : backspace 앞의 한칸 지우기
* u : Undo(Ctrl+z)
* r : 그자리의 한글자만 바꾸기
* A(shift + a) : insert mode at line end, 라인끝에서 입력모드 시작
* o : 다음줄에 입력모드 시작
* O(shift + o) : 위에 줄에서 입력모드 시작
* dd : 한줄 지우기
* cw : 한단어를 바꿔라. c는 무조건 change이며 w는 word를 의미한다.
* dw : 한단어를 삭제해라. d는 delete

### 블럭지정 및 복사
* v : 블럭 지정모드
* y : 복사(ctrl+c)
* 블럭지정 후 d : 블럭만큼 삭제
* D(Shift + d) : 현재 커서위치 뒷부분 삭제
* yy : 한개의 라인을 복사
* p : 붙여넣기


## colon command(명령모드)
**모두 : 를 붙이고 시작하자.**
* w : save
* q : quit
* wq : 저장하고 나가라. (w와 q를 함께 사용)
* q! : 저장하지 않고 그냥 나가기
* set nu : line number를 보여줘
* set nonu : line number를 지워줘
* set paste : 붙여넣기, 파이썬과 같은 경우 indentation이 깨지는것을 방지하기 위한 붙여넣기
* %s/pts/ttt(/g) : %s는 replace역할을 하며, pts를 ttt로 바꾸겠다는 의미이다. 여기서 g를 넣으면 global 즉 모두 바꾸게 된다.
  * %s/찾을문자/바꿀문자/ig : ig는 ignore case로 대소문자 구별없이 모두 바꾸겠다는 것.
### search(명령모드)
* /검색어 : 검색어로 커서가 간다. "끝까지 찾았음, 처음부터 계속" 이 나온다면 모두 다 찾은 것이다.
  * n,N(Shift + n) : 검색어를 찾은 후 n은 After, N은 Before
* 라인번호 : :1 을 하면 첫번째 라인으로 넘어간다. 즉 해당 숫자의 라인으로 이동
  * $ : :$를 하면 맨 마지막 라인으로 이동한다.
 
--------

### vim 에디터 도중 파이썬 결과를 볼수 있다?!
vim 에디터를 킨 상태에서, :!<파이썬 실행> <실행할 파일 이름>을 사용한다면 vim에디터를 나가지 않고 결과를 확인 할 수 있다.

* :w : 파일을 수정한 상태라면, :w를 실행해 저장 후 실행하자.
