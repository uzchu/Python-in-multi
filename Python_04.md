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