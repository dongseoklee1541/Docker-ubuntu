# shell script?
shell script란 shell에서 한줄씩 실행되는 코드라고 생각하면 좋다.

## 기본 문법
shell 파일은 기본적으로 아래 문장을 쓰고 시작한다.
* #!/bin/sh or #!/bin/bash : sh로 실행할것인가 bash로 실행할 것인가의 의미. 보통 bash를 많이 사용한다

* echo "hello world" : print와 동일
  * cf. string은 ""가 없어도 상관없다. 그러나 "hello world"와 같이 띄어쓰기가 있어도 한묶음으로 쓰고 싶을때 ""를 사용해서 알려주는 것.
* printf "%s %s %d\n" aa bb 123 : c언어의 printf와 비슷함

* str = "hello" : string 선언할때 사용
  * echo "${str} world" or "$str world" : 변수를 사용할때는 $를 앞에 붙여주고 사용한다.
  * "\${str} world" : 그냥 $를 사용하고 싶다면 앞에 \를 붙여준다.
  
  
