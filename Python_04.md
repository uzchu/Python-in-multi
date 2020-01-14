# 내장함수

##### abs

: 절대값을 돌려주는 함수

##### all

:모두 참이면 True, 하나라도 거짓이면 False

##### any (all 반대)

:하나라도 참이 있으면 True, 모두 거짓일때만 False

##### chr

:ASCII코드 값에 해당하는 문자 출력

##### dir

:객체가 가지고 있는 변수나 함수 보여줌

```python
a = "hello"
dir(a)
>>> ['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '_
_eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs
__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__'
, '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__',
'__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__'
, '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'e
ncode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isal
num', 'isalpha', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric',
 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstr
ip', 'maketrans', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartitio
n', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase'
, 'title', 'translate', 'upper', 'zfill']
```

##### divmod

:몫과 나머지 튜플형태로 돌려줌

##### enumerate

: 인덱스와 값을 포함하는 객체로 돌려줌 (for문과 함께 자주 사용)

##### eval

:실행가능한 문자열을 입력받아 실행한 결과값을 돌려주는 함수

##### :star:filter

: 첫번째 인수로 함수, 두번째 인수로 반복가능한 자료형을 입력받아 함수에 입력되었을때 참인것만 묶어서 돌려줌(return값이 true,false형만 가능함)

간단한 함수의 경우 lambda 사용시 간단한 코드작성 가능

##### hex

:정수값을 16진수로

##### id

:객체의 고유주소값

##### input

:사용자의 입력을 받는 함수

##### int

: 문자열형태의 숫자 or 소수점있는 숫자를 정수로 반환

##### isinstance

:첫번째 인수로 인스턴스, 두번째 인수로 클래스이름

인스턴스가 클래스에 해당하면 True아니면 False

##### len

:입력값의 길이(요소의 전체 갯수) 돌려주는 함수

##### :star:map

:함수와 반복가능한 자료형을 입력받아 수행한 결과 돌려주는 함수 (filter와 유사하나 true,false형 외의 것도 가능함 좀 더 범용적)

##### oct

:정수를 8진수 문자열로

##### open

:파일 이름과 읽기방법을 입력받아 파일객체를 돌려줌 (읽기방법 생략시 'r')

| mode | 설명          |
| ---- | ------------- |
| w    | 쓰기모드      |
| r    | 읽기모드      |
| a    | 추가모드      |
| b    | 바이너리 모드 |

##### ord(chr 반대)

:문자의 아스키코드 값을 돌려줌

##### pow

: pow(x,y) >> x <sup>y </sup>

##### range

: for문과 함께 자주사용

인수가 1개 (0부터 시작, 1씩 증가)

인수가 2개 (두개의 인수는 시작, 끝 숫자를 말함. 끝 숫자는 포함X,1씩증가)

인수가 3개 (세번째 인수씩 만큼 증가)

##### round

:반올림

##### sorted

:정렬

##### str

:문자열로

##### sum

:리스트나 튜플 요소 합계

##### type

:자료형이 뭔지

##### :star:zip

:동일한 개수로 이루어진 자료형을 묶어주는 역할 (같은 위치)

```
list(zip([1,2,3],[4,5,6]))
>> [(1,4),(2,5),(3,6)]
```



# 외장함수

##### sys

:파이썬 인터프리터가 제공하는 변수와 함수를 직접 제어할 수 있게 해주는 모듈

(추후 추가 공부..)

##### pickle

:객체의 형태를 유지하면서 파일에 저장하고 불러올 수 있게하는 모듈

pickle.dump로 저장, pickle.load로 불러옴

```python
import pickle
f = open("test.txt",'wb')
data = {1:'python', 2:'you need'}
pickle.dump(data,f)
f.close()

import pickle
f = open("test.txt",'rb')
data = pickle.load(f)
print(data)
{2:'you need',1:'python'}
```

##### glob

:디렉터리에 있는 파일들을 리스트로 만들어줌, 메타문자를 사용해 원하는 파일만 읽어올 수도 있음

```python
파일이름이 mark로 시작하는 파일 모두 불러올 때
import glob
glob.glob('c:/doit/mark*')
>>
['c:doit\\marks1.py','c:doit\\marks2.py','c:doit\\marks3.py']
```

##### webbrowser

:웹브라우저를 자동으로 실행하는 모듈

```python
import webbrowser
webbrowser.open('http:/google.com')
새로운 창 열 때
webbrowser.open_new('http://google.com')
```

# 정규표현식

##### 정규표현식 지원모듈 (re)

```
import re
p = re.compile('ab*')
```

##### 메타문자

:메타 문자란 원래 그 문자가 가진 뜻이 아닌 특별한 용도로 사용하는 문자

<center>`. ^ $ * + ? { } [ ] \ | ( )`</center>

##### 문자클래스[]

:[]사이의 문자들과 매치

`-` : (from - to)범위 의미

`^` : 반대(not) 의미

##### Dot(.)

`a.b` : a + 모든 문자+b

`a[.]b` : a + . + b (문자 . 그대로 의미)

##### 반복(*)

:*앞에 있는 문자가 0부터 무한대로 반복될 수 있다는 의미(메모리상 2억개까지만 가능)

##### 반복(+)

:*가 0부터라면, +는 1부터

##### 반복({m,n})

: {m} 반드시 m번 반복 되는 것만 매치

{m,n} m에서 n번 사이(이상,이하)로 반복되는 것만 매치

? 있거나 없거나 둘다 매치







