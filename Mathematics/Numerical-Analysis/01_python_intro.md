# 1️⃣ python_intro

## 1. 파이썬 소개

- 공개 무료 소프트웨어

- 매우 강력한 모듈이 있어 응용 분야가 다양함.


### 1.1 파이썬의 장점

- 고품질 소프트웨어
- 가독성
- 재사용성
- 유지 보수의 수월성
- 개발자의 고생산성
- 프로그램의 이식성(portability)
- 코딩은 간단하고 가독성이 좋음.


### 1.2 파이썬의 단점

- 인터프리터 방식으로 실행 속도가 느릴 수 있음
- 실행 속도를 높일 수 있는 다른 방식 존재
- C/C++ 등으로 최적화된 이진 파일 사용 가능


## 2. 객체(Object)

파이썬의 모든 것은 객체이다.
- 값(value)
- 타입(type)
- 속성(attribute)

### 2.1 객체 유형 예시

| 유형 | 예시 |
|------|------|
| 숫자형 | int, float, complex |
| 시퀀스형 | string, list, tuple |
| 매핑형 | dict |
| 집합형 | set |
| 함수형 | function |
| 프로그램 단위 객체 | 함수, 모듈, 클래스 |

## 3. 기본 자료형

### 3.1 숫자형(Number)
* 정수(integer) ``` x = 1 ```
* 실수(floating-point)  ``` pi = 3.14 ```
* 복소수(complex) ``` z = 3 + 4j ```

### 3.2 문자열(Strings)

문자열은 문자들의 순서 있는 집합(sequence)이다.

```python
>>> S = 'Spam'
>>> T = "Python"
```

- 길이

    ```python
    >>> len(S)
    4
    ```
- 인덱싱(indexing)
    ```python
    >>> S[0]
    'S'
    ```

    ```python
    >>> S[1]
    'p'
    ```

    ```python
    >>> S[-1]
    'm'
    ```

    ```python
    >>> S[-2]
    'a'
    ```

- 슬라이싱(slicing)

    ```python
    >>> S[1:3]
    'pa'
    ```

    ```python
    >>> S[0:2]
    'Sp'
    ```

    ```python
    >>> S[:2]
    'Sp'
    ```

    ```python
    >>> S[2:]
    'am'
    ```

    ```python
    >>> S[:]
    'Spam'
    ```

- 간격(step)

    ```python
    >>> S[0:4:2]
    'Sa'
    ```

    ```python
    >>> S[::2]
    'Sa'
    ```

    ```python
    >>> S[::-1]
    'mapS'
    ```

#### 3.2.1 문자열 연산

- 결합(concatenation)

    ```python
    >>> 'Spam' + 'Egg'
    'SpamEgg'
    ```

-  반복(repetition)

    ```python
    >>> 'ha' * 3
    'hahaha'
    ```

- 포함 여부

    ```python
    >>> 'pa' in 'Spam'
    True
    ```

    ```python
    >>> 'xy' in 'Spam'
    False
    ```

#### 3.2.2 문자열은 immutable
문자열은 수정 불가능 객체이다.

```python
>>> S = 'Spam'
>>> S[0] = 'X'
Traceback (most recent call last):
TypeError
```

새 문자열을 만들어야 한다.

```python
>>> 'X' + S[1:]
'Xpam'
```

#### 3.2.3 문자열 메서드
- 대문자 / 소문자

    ```python
    >>> S = 'Spam'
    >>> S.upper()
    'SPAM'
    ```

    ```python
    >>> S.lower()
    'spam'
    ```

-  공백 제거

    ```python
    >>> line = ' aaa,bbb,ccccc,dd   '
    >>> line.strip()
    'aaa,bbb,ccccc,dd'
    ```

    ```python
    >>> line.rstrip()
    ' aaa,bbb,ccccc,dd'
    ```

    ```python
    >>> line.lstrip()
    'aaa,bbb,ccccc,dd   '
    ```

- 분리(split)

    ```python
    >>> line = 'aaa,bbb,ccccc,dd'
    >>> line.split(',')
    ['aaa', 'bbb', 'ccccc', 'dd']
    ```

    ```python
    >>> line.rstrip().split(',')
    ['aaa', 'bbb', 'ccccc', 'dd']
    ```

- 찾기(find)

    ```python
    >>> 'Spam'.find('pa')
    1
    ```

    ```python
    >>> 'Spam'.find('xy')
    -1
    ```

- 치환(replace)

    ```python
    >>> 'Spam'.replace('pa', 'XY')
    'SXYm'
    ```

#### 3.2.4 문자열 포맷팅

- old style %

    ```python
    >>> '%s, eggs, and %s' % ('spam', 'SPAM!')
    'spam, eggs, and SPAM!'
    ```

- format()

    ```python
    >>> '{0}, eggs, and {1}'.format('spam', 'SPAM!')
    'spam, eggs, and SPAM!'
    ```

    ```python
    >>> '{}, eggs, and {}'.format('spam', 'SPAM!')
    'spam, eggs, and SPAM!'
    ```

- 숫자 포맷

    ```python
    >>> '{:,.2f}'.format(296999.25687)
    '296,999.26'
    ```

    ```python
    >>> '%.2f | %+05d' % (3.14159, -42)
    '3.14 | -0042'
    ```

    ```python
    >>> '{0:,.2f} is not {1:d}.'.format(234534353.34343, 343434)
    '234,534,353.34 is not 343434.'
    ```

## 4. 내장 자료구조
| 자료형  | 여러 값 저장      | 순서     | 중복 허용 |
| ---- | ------------ | ------ | ----- |
| 리스트  | O            | O      | O     |
| 튜플   | O            | O      | O     |
| 딕셔너리 | O(key-value) | key 기반 | key X |
| 집합   | O            | X      | X     |



### 4.1 리스트(List)

리스트는 **순서가 있는 변경 가능한(mutable) 자료형**이다.


```python id="l1w8fa"
>>> L = [123, 'spam', 1.23]
>>> L
[123, 'spam', 1.23]
````

- 길이

    ```python id="e4w0kn"
    >>> len(L)
    3
    ```

- 인덱싱

    ```python id="tr6m8q"
    >>> L[0]
    123
    ```

    ```python id="g0n4zc"
    >>> L[-1]
    1.23
    ```

- 슬라이싱

    ```python id="p9a2dl"
    >>> L[1:]
    ['spam', 1.23]
    ```

    ```python id="bh8yut"
    >>> L[:2]
    [123, 'spam']
    ```

-  리스트 연결 / 반복

    ```python id="z4v7fk"
    >>> [1,2] + [3,4]
    [1, 2, 3, 4]
    ```

    ```python id="m8sa2q"
    >>> ['ha'] * 3
    ['ha', 'ha', 'ha']
    ```

#### 4.1.1 리스트는 mutable

```python id="k6xn9w"
>>> L = [1,2,3]
>>> L[0] = 99
>>> L
[99, 2, 3]
```

#### 4.1.2 리스트 메서드
- append()

    ```python id="e2mwqa"
    >>> L = [1,2,3]
    >>> L.append(4)
    >>> L
    [1,2,3,4]
    ```

- pop()

    ```python id="j3t4pc"
    >>> L.pop()
    4
    >>> L
    [1,2,3]
    ```

-  insert()

    ```python id="r8x7zn"
    >>> L.insert(1, 99)
    >>> L
    [1,99,2,3]
    ```

-  remove()

    ```python id="u2p0wr"
    >>> L.remove(99)
    >>> L
    [1,2,3]
    ```

- sort()

    ```python id="n5b9xa"
    >>> L = [3,1,4,2]
    >>> L.sort()
    >>> L
    [1,2,3,4]
    ```

- reverse()

    ```python id="h1z4vt"
    >>> L.reverse()
    >>> L
    [4,3,2,1]
    ```

#### 4.1.3 중첩 리스트

```python id="q6d9ma"
>>> M = [[1,2,3],
...      [4,5,6],
...      [7,8,9]]
```

```python id="k4y0rp"
>>> M[1]
[4,5,6]
```

```python id="t9w1zb"
>>> M[1][2]
6
```

####  4.1.4 리스트 내포(List Comprehension)

```python id="w5z7na"
>>> [x**2 for x in range(5)]
[0,1,4,9,16]
```

```python id="g2v6cq"
>>> [x for x in range(10) if x % 2 == 0]
[0,2,4,6,8]
```

## 4.2 튜플(Tuple)

튜플은 리스트와 유사하지만 **수정 불가(immutable)** 이다.

```python id="u9r2xa"
>>> T = (1,2,3)
>>> T[0]
1
```

```python id="j6n8ty"
>>> T[0] = 99
Traceback (most recent call last):
TypeError
```
 한 개짜리 튜플은 쉼표가 필요하다.

```python id="s3f9pe"
>>> T = (5,)
```
 튜플 패킹 / 언패킹

```python id="a7v5mn"
>>> x, y, z = (1,2,3)
>>> x
1
```

## 4.3 딕셔너리(Dictionary)

키(key)-값(value) 구조 자료형

```python id="v4n0yw"
>>> D = {'a':1, 'b':2}
>>> D
{'a':1, 'b':2}
```

-  접근

    ```python id="q8m1sx"
    >>> D['a']
    1
    ```

-  추가 / 수정

    ```python id="f0x7ra"
    >>> D['c'] = 3
    >>> D
    {'a':1,'b':2,'c':3}
    ```

### 4.3.1 주요 메서드

```python id="m2y6vz"
>>> D.keys()
dict_keys(['a','b','c'])
```

```python id="p5q1lu"
>>> D.values()
dict_values([1,2,3])
```

```python id="h7z3nm"
>>> D.items()
dict_items([('a',1), ('b',2), ('c',3)])
```

-  get()

    ```python id="y8w4tp"
    >>> D.get('a')
    1
    ```

    ```python id="k3v6rb"
    >>> D.get('x', 0)
    0
    ```

### 4.4 집합(Set)

중복 없는 자료형

```python id="b4m7xp"
>>> S = {1,2,3,2,1}
>>> S
{1,2,3}
```

- 연산

    ```python id="t1n9aw"
    >>> A = {1,2,3}
    >>> B = {3,4,5}
    ```

- 집합

    ```python id="w6r3zk"
    >>> A | B
    {1,2,3,4,5}
    ```

- 교집합

    ```python id="x2c8pf"
    >>> A & B
    {3}
    ```

- 차집합

    ```python id="d7m4vb"
    >>> A - B
    {1,2}
    ```

## 5. 제어문

### 5.1 조건문 (if)

조건에 따라 코드 실행을 분기한다.

- if - else

    ```python id="r9w2za"
    >>> x = -3

    >>> if x > 0:
    ...     print("positive")
    ... else:
    ...     print("negative")
    ...
    negative
    ```

-  if - elif - else

    ```python id="v6p3dn"
    >>> score = 85

    >>> if score >= 90:
    ...     print("A")
    ... elif score >= 80:
    ...     print("B")
    ... elif score >= 70:
    ...     print("C")
    ... else:
    ...     print("F")
    ...
    B
    ```

### 5.2 반복문 (while)

조건이 참인 동안 반복 실행한다.

- 무한 루프

    ```python
    while True:
        ...
    ```

- break

    ```python id="f2m6pe"
    >>> x = 0

    >>> while True:
    ...     if x == 3:
    ...         break
    ...     print(x)
    ...     x += 1
    ...
    0
    1
    2
    ```

- continue

    ```python id="z7w4mt"
    >>> for x in range(5):
    ...     if x == 2:
    ...         continue
    ...     print(x)
    ...
    0
    1
    3
    4
    ```

### 5.3 반복문 (for)

시퀀스 자료형 순회

```python id="y8x1ka"
>>> for x in [1,2,3]:
...     print(x)
...
1
2
3
```
-  range()

    ```python id="p6n4we"
    >>> list(range(5))
    [0,1,2,3,4]
    ```

    ```python id="m3r9zb"
    >>> list(range(1,6))
    [1,2,3,4,5]
    ```

    ```python id="d8k1ua"
    >>> list(range(0,10,2))
    [0,2,4,6,8]
    ```

- 문자열 순회

    ```python id="u5q7vt"
    >>> for ch in "spam":
    ...     print(ch)
    ...
    s
    p
    a
    m
    ```

## 6. 함수
함수(Function)

함수는 재사용 가능한 코드 블록이다.

```python id="h7x2mc"
>>> def add(a, b):
...     return a + b
...
```

```python id="g1m8pa"
>>> add(3,4)
7
```

-  기본 인수(default argument)

    ```python id="q9z5tn"
    >>> def power(x, n=2):
    ...     return x ** n
    ...
    ```

    ```python id="w2r7bf"
    >>> power(3)
    9
    ```

    ```python id="c4m0ya"
    >>> power(3,3)
    27
    ```

-  키워드 인수

    ```python id="j6n1tp"
    >>> power(n=3, x=2)
    8
    ```

- 가변 인수

    ```python id="r5x8vu"
    >>> def total(*args):
    ...     return sum(args)
    ...
    ```

    ```python id="f9m2ek"
    >>> total(1,2,3,4)
    10
    ```


### 6. 변수 범위(scope)
- 지역 변수(local)와 전역 변수(global)는 다르다.

    ```python id="n1v7wa"
    >>> x = 10

    >>> def f():
    ...     x = 20
    ...     print(x)
    ...
    ```

    ```python id="z3p8cr"
    >>> f()
    20
    >>> x
    10
    ```
-  global

    ```python id="s7k4py"
    >>> x = 10

    >>> def f():
    ...     global x
    ...     x = 99
    ...
    ```

    ```python id="b6n9qe"
    >>> f()
    >>> x
    99
    ```

## 7. 모듈과 파일

### 7.1. 모듈

모듈은 도구들의 모임 역할을 하는 프로그램이다.

모듈 안에는 변수들이 정의되어 있다.

이 변수 이름들의 집합을 namespace(이름 공간)이라 한다.

예제 파일: `threenames.py`

```python
a = 'abc'
b = 'bcd'
c = 'cde'

print(a, b, c)
````

사용 예:

```python
>>> import threenames
abc bcd cde

>>> threenames.b
'bcd'

>>> threenames.c
'cde'
```

#### 7.1.1 math 모듈
```python
>>> import math
>>> math.sqrt(85)
9.219544457292887
```
- 모듈을 불러오지 않으면:
    ```python
    >>> sqrt(85)
    Traceback (most recent call last):
    NameError: name 'sqrt' is not defined
    ```
#### 7.1.2 random 모듈
- random() : 0 이상 1 미만 실수 난수
    ```python
    >>> import random
    >>> random.random()
    0.37444887175646646
    ```
- randint(a,b) : a~b 정수 난수
    ```python
    >>> random.randint(1, 10)
    7
    ```
- choice(seq) : 시퀀스에서 임의 선택
    ```python
    >>> random.choice(['a', 'b', 'c'])
    'b'
    ```

### 7.2 파일 입출력

-  쓰기(write)

    ```python id="y1q7bd"
    >>> f = open('test.txt', 'w')
    >>> f.write('hello')
    5
    >>> f.close()
    ```

- 읽기(read)

    ```python id="k8m4ra"
    >>> f = open('test.txt', 'r')
    >>> f.read()
    'hello'
    >>> f.close()
    ```

- with 문: 자동으로 close 된다.

    ```python id="m7x1te"
    >>> with open('test.txt', 'r') as f:
    ...     data = f.read()
    ...
    ```

## 8. 오류 처리

```python id="p3v6zu"
>>> try:
...     1 / 0
... except ZeroDivisionError:
...     print("error")
...
error
```

- finally

    ```python id="w8m2nc"
    >>> try:
    ...     pass
    ... finally:
    ...     print("end")
    ...
    end
    ```

## 9. 객체지향 프로그래밍

### 9.1 클래스와 메서드

-  클래스(Class)

    ```python id="j2x7qa"
    >>> class Person:
    ...     def __init__(self, name):
    ...         self.name = name
    ...
    ```

    ```python id="r4v9me"
    >>> p = Person("Lee")
    >>> p.name
    'Lee'
    ```

-  메서드(method)

    ```python id="h1n6tb"
    >>> class Person:
    ...     def hello(self):
    ...         print("Hi")
    ...
    ```

    ```python id="g7p3cx"
    >>> p = Person()
    >>> p.hello()
    Hi
    ```