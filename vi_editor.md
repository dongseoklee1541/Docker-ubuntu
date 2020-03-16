## vim 을 사용하는 이유?
마우스 없이 모든걸 할 수 있는 편집기라는 장점


# vi Editor

* 명령(command) mode --> 편집 mode : 명령모드에서 i(insert, 끼워넣기) 또는 a(append, 뒤에 이어넣기) 를 눌러서 편집모드로 전환한다.

* 편집 모드 --> 명령 모드 : 편집모드에서 esc


### 방향 전환
h,j,k,l 로 방향을 이동할 수 있다. h는 좌 l은 우 j는 아래 마지막으로 k는 위다. 

* w : 단어 단위로 이동
* ctrl + f or u/b : f는 페이지 다운, u는 페이지 업이다.

### 수정
* x : 한칸 지우기
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
모두 : 를 붙이고 시작하자.
* w : save
* q : quit
* wq : 저장하고 나가라. (w와 q를 함께 사용)
* set nu : line number를 보여줘
* set nonu : line number를 지워줘
* paste : 

### search(명령모드)
- /검색어 
