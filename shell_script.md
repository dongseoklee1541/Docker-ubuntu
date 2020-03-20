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
  
  
### loop
* for문
```
for i in {1..100}; do ~ ; done

#1 부터 100까지 출력하는 문장
for i in {1..100};do echo $i; done

#ls 를 통해서 txt 파일 내용 출력하기
for i in `ls *.txt`;do cat $i;done
```

### alias
alias란 별명을 짓는다. 긴 명령어의 반복을 줄이고 싶을때 주로 사용한다.
```
alias s= '~/s1.sh`
s # s만 입력해도 ~/s1.sh가 실행됨
```
하지만. 이 경우 alias는 재시작하면 없어진다. 재시작해도 남아있게 하고 싶다면, .bashrc에 내용을 추가해줘야 한다.

### Variables
$를 붙인다면 각 변수들을 의미한다. $0은 자신, $1은 첫번째 파라미터, $2는 두번째 파라미터.. 이런 식으로. $#은 파라미터의 갯수를 나타낸다.
```
~$ ./s3.sh aaa bbb

$0 = ./s3.sh
$1 = aaa
$2 = bbb
$# = 2
```

### IF

* gt : greater than , >
* lt : less than , <
* eq : equal, ==
* ne : not equal, !=
* le : less equal, <=
* ge : greater than equal , >=

매개변수로 파일을 넣었을때, 그 파일을 읽어오는 sh를 만들어보자.
```
#!/bin/bash

if [ $# eq 0 ]; then  ==> 괄호를 쓸때는 한칸씩 띄어쓰고 작성해야한다.
 echo "please give me file."
 echo "usage) ./s4.sh <format-file> <date-file> <test-file>"
 exit 0 ==> 종료
fi

cat $1
```

### date
date는 현재 날짜를 반환해준다. 포멧을 바꿔서 나타내고 싶다면?
```
date "+%Y-%m-%d %H:%M:%S" => 연-월-일 시-분-초 형식으로 출력됨

# 오늘날짜가 아닌 다른날짜를 출력하고 싶다면..
ATE=`date +%Y-%m-%d --date=yesterday`
DATE=`date +%Y-%m-%d --date='1 day ago'`
DATE=`date +%Y-%m-%d --date='2 day ago'`
DATE=`date +%Y-%m-%d --date='2 day'`
DT=`date +%Y-%m-%d --date='1 week ago'`
DT=`date +%Y-%m-%d --date='1 month ago'`
DT=`date +%Y-%m-%d --date='1 month'`

```

### 구구단
```
#!/bin/bash

for i in {2..9}
do
    for j in {1..9}
    do
        echo "$i * $j = $(( $i * $j ))" # (( $i * $j )) ((  ))을 넣은이유는, $i 을 string으로 받지 말고 연산하라 라는 의미.
    done
    echo "--------------------------------"
done
```




