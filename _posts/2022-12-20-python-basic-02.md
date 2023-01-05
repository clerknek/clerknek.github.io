---
title: '[Python 기초] 02. 테이터타입'
date: 22-12-20 21:12:10 +0800
categories: ['Python', 'Python 기초']
tags: [python]     # TAG names should always be lowercase
---

# 변수와 함수/연산자

<strong style='color:red;font-size:1.5em'>프로그램이 하는 일</strong>
<p>
<span style="font-size:1.2em">- 정보(데이터)를 처리한다.</span>  
    

- <b style='font-size:1.2em'>정보(데이터)</b>: **변수(Variable)**`메모리 상의 공간` **와 값(Value)** 로 프로그램에 표현한다.
- <b style='font-size:1.2em'>처리한다</b>: **연산자(Operator)와 함수(Function)** 으로 프로그램에 표현한다.
    
> 표현(Expression): 어떤 것을 코드에 작성하는 방법을 표현(Expression)이라고 한다.  
> 예를 들어 프로그램에 숫자 십을 표현할 때 `10` 이라고 한다. 이런 것을 정수의 표현/표현식 이라고 한다.

# 변수 (Variable)
- 데이터를 저장하는 메모리 공간
- 이 메모리 공간은 이름(변수이름)으로 관리된다.
    - 그래서 변수이름은 우리가 사용하는 값의 이름으로 사용된다.
    
## 변수 선언및 초기화
- 변수명 = 값
    - 변수는 반드시 선언하면서 값을 대입 해야 한다.
    - 선언시 대입할 값이 없으면 None을 대입 (`name = None`)

  
### 식별자 규칙과 변수이름 주는 관례

#### 식별자 규칙
- 식별자란 파이썬에서 사용하는 것들을 구분하기 위해 주는 이름을 말한다. 
- 사용할 수 있는 문자는 **일반 문자**(영어 알파벳 뿐 만 아니라 한글 한자 등 모든 일반 문자를 사용할 수 있다.), **숫자, 특수 문자는  _(underscore) 만** 가능.
- 숫자는 **두번째 글자** 부터 사용할 수 있다.
- **예약어(keyword, reserved word)**는 사용할 수 없다.
- 대소문자를 구별한다.

> <b style='font-size:1.2em'>파이썬 키워드</b>
> ```python
> False      await      else       import     pass
> None       break      except     in         raise
> True       class      finally    is         return
> and        continue   for        lambda     try
> as         def        from       nonlocal   while
> assert     del        global     not        with
> async      elif       if         or         yield
> ```

#### 변수이름 관례
- 모든 글자를 소문자로 한다.
- 여러단어를 조합할 경우 `_` 로 구분한다. (snake 표기법)
- 예: `name`, `age`, `customer_name`, `product_id`, `sale_price`


```python
name = "전종민"
age = 24
address = "서울시 동작구"
```


```python
name
```




    '전종민'




```python
age
```




    24




```python
address
```




    '서울시 동작구'



- REPL로 인해 맨 아래있는 값만 출력한다.


```python
name
age
address
```




    '서울시 동작구'



> **print()함수**
> - ( ) 안에 전달해주는 값(Argument)을 문자열로 변환 후 화면(Teminal)에 출력하는 함수
>     - 값에 엔터를 붙인뒤 출력한다.
> - 여러개의 값을 출력할 경우 나열해서 전달하면 된다.
> - 여러개개의 값을 출력할 경우 구분자는 공백을 기본값으로 한다. 다른 구분자를 사용할 경우 `sep=구분자문자열`를 전달한다.
> - 뒤에 엔터 대신 다른 값을 붙일 경우 `end=붙일문자열` 을 전달한다.


```python
print(name)
print(age)
print(address)
```

    전종민
    24
    서울시 동작구
    


```python
print(name, age, address)
print(name, age, address, sep = " / ")
```

    전종민 24 서울시 동작구
    전종민 / 24 / 서울시 동작구
    


```python
print(name, end = "===")
print(age, end = "")
print(address)
```

    전종민===24서울시 동작구
    

## 변수 사용
- 변수를 사용하는 것은 변수에 값을 변경(대입)과 변수가 가진 값을 조회하는 두가지가 있다.

### 변수에 값 대입/할당 (assignment)
1. 변수명 = 값
    - `=`을 기준으로 왼쪽은 변수, 오른쪽은 대입할 값
    - 대입할 값으로 다음이 올 수 있다.
        - Literal 값(값 표현식) -> 값을 쓴 것 ex) 34(O), 34+2(X)
        - 다른 변수
        - 연산식
    - 변수 초기화와 변수값 변경의 파이썬 구문은 동일하다. 변수를 처음 만들고 값을 대입하면 초기화이고 그 이후 할당하는 것들은 변경이 된다.
 

2. 여러 변수에 동일 한 값 대입
    - a = b = c = 30

3. 여러 변수에 다른 값 대입을 한 구문으로 처리
    - `a, b, c = 10, 20, 30`


```python
print(name)
name = "홍길동" # 기존 name 변수에 값을 "홍길동"으로 변경
print(name)
```

    전종민
    홍길동
    


```python
이름 = name # name 변수의 값을 이름 변수에 대입
print(이름)
```

    홍길동
    


```python
나이 = age * 2 # age 변수가 가진 값에 2를 곱한 결과를 나이 변수에 대입
print(나이)
```

    48
    


```python
no1 = no2 = no3 = no4 = 30
print(no1, no2, no3, no4)
```

    30 30 30 30
    


```python
id, price = "id-1", 300000
print(id, price)
```

    id-1 300000
    

4. 대입(할당) 연산자(Assignment operator)

- 변수의 값을 그 변수와 다른 값을 연산한 결과로 변경한다.
|연산자|예|동일연산|
|:-|-|-|
|=|x = 1|x = 1	
|+=|x += 1|x = x + 1|	
|-=|x -= 1|x = x - 1|	
|*=|x *= 1|x = x * 1|	
|/=|x /= 1|x = x / 1|	
|%=|x %= 1|x = x % 1|	
|//=|x //= 1|x = x // 1|	
|\*\*=|x \*\*= 1|x = x \*\* 1|


```python
num = 30
print(num)
num = num + 50
print(num)
num += 100 # num = num + 100
print(num)
num -= 50  # num = num - 50
print(num)
```

    30
    80
    180
    130
    

### 변수값 조회
- 값을 사용해야 하는 자리에 변수명을 표현하면된다.
    - 변수명을 쓰면 그 변수가 가진 값을 조회해 사용한다.


```python
name = "전종민"
print("전종민")
print(name)
new_age = age + 20
print(age, new_age)
```

    전종민
    전종민
    24 44
    

## 변수를 메모리에서 제거

메모리에서 변수(데이터 저장공간)을 제거할 때는 `del 변수명` 명령어를 사용한다.


```python
print(name)
del name  # 메모리에서 name을 제거
print(name)
```

    전종민
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_18776\1256582049.py in <module>
          1 print(name)
          2 del name  # 메모리에서 name을 제거
    ----> 3 print(name)
    

    NameError: name 'name' is not defined



```python
print(age)
del age
print(age)
```

    24
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_18776\2249055351.py in <module>
          1 print(age)
          2 del age
    ----> 3 print(age)
    

    NameError: name 'age' is not defined


# 데이터 타입 (Data Type)

- 값들의 형태(type)에 따라 종류를 분류한 것
- 데이터타입은 값을 표현하는 방식과 관련 연산자들을 익히도록 한다.

## None 값
- 아무 값도 없음을 나타내는 값  ```(변수가 비어 있는 것은 아님! None이라는 값을 가지고 있음)```


```python
name = None
age1 = age2 = age3 = None
```


```python
name
```


```python
print(name, age1, age2, age3)
```

    None None None None
    

## 숫자형(Numeric) - 정수, 실수

- 정수(int)와 실수(float) 형이 있다.
    - **정수 표현식**
        - 10, 20, -1, -20, 0
        - 16진수 표기
            - 0x 로 시작 (0xAF29)
        - 8진수 표기
            - 0o 으로 시작 (0o71)
    - **실수**
        - 20.1, 0.123411, 15.2321598
        - 지수표기법
            - $5e7$ -> $5.0\times10^7$
            - $3e-7$ -> $3\times10^{-7}$


```python
print(0x53)  #16진수를 10진수로 변환후 출력
print(0o73)  # 8진수를 10진수로 변환후 출력
```

    83
    59
    


```python
print(5e2)  # 5 * 10**2
print(3e-3) # 3 * 10**-3
```

    500.0
    0.003
    

### 연산자
<b style='font-size:1.2em'>산술연산자</b>

|Operator(연산자)|설명|예|
|-|-|-|
|+|덧셈|x + y|
|-|뺄셈|x - y|
|*|곱셈|x * y|
|/|나눗셈|x / y|
|%|Modulus(나머지 나누기 연산자)|x % y|
|//|Floor division(몫 나누기 연산자)|x // y|
|**|제곱연산|x ** y|


```python
num1, num2 = 10, 3
print(num1, num2)
print(num1 + num2)
print(num1 - num2)
print(num1 * num2)
print(num1 ** num2)
```

    10 3
    13
    7
    30
    1000
    


```python
print(num1 / num2)
print(num1 // num2)
print(num1 % num2)
```

    3.3333333333333335
    3
    1
    

## 논리형(bool)
- **참(True)과 거짓(False)을** 표현하는 데이터 타입
    - 제어문에서 많이 사용된다.
- 값 표현식
    - True, False
- bool 값이 들어가야 하는 구문에 다른 타입의 값을 작성하면 자동적으로 bool 타입으로 변환된다. (묵시적 형변환이라 한다.)
    - **0글자의 문자열, 숫자 0, None, 원소가 하나도 없는 자료구조는** False로 변환되고 그 이외는 True로 변환된다.


```python
print(True, False)
```

    True False
    

- input(\[label\]) 함수
    - 사용자로 부터 값을 입력받을 때 사용한다.
    - 사용자의 입력을 기다렸다 사용자가 값을 입력하고 엔터를 치면 그 입력한 값을 읽어 반환한다.
    - 어떤 값을 입력받을 것인지 Label을 **문자열**로 전달할 수 있다.


```python
s = input("이름:")
print(s)
```

    이름:전종민
    전종민
    

### 논리형 관련 연산자
<b style='font-size:1.2em'>비교 연산자</b>
- 결과가 bool 타입
- 기준은 왼쪽의 피연산자이다.
|연산자|설명|예|
|-|-|-|
|==|같은가?|x == y|	
|!=|같지 않은가?|x != y|	
|>|x가 큰가?|x > y|
|<|x가 작은가?|x < y|	
|>=|x가 크거나 같은가?|x >= y|
|<=|x가 작거나 같은가?|x <= y|


```python
"가나다라" < "다라"
```




    True



<b style='font-size:1.2em'>논리 연산자</b>
- 피연산자가 bool 타입이고 결과도 bool 타입이다.
- &, |, ^ 기호를 연산자로 사용할 때는 피연산자를 ( )로 묶어 줘야 한다. ```기호를 먼저 연산해버림```
|연산자|설명|예|
|:-|-|-|
|and, &|피연산자 모두 True이면 True를 하나라도 False이면 False를 반환.|x > 5 and  x < 10|	
|or, \||피연산자 둘중 하나만 True이면 True를 둘다 False이면 False를 반환.|x > 5 or x < 4|
|^|XOR 연산. 피연산자가 다를 경우 True, 같으면 False를 반환.|(x > 5) ^ (x < 4)|
|not|단항연산자. 결과를 뒤바꾸어 반환. True는 False로 False는 True로 반환.|not(x < 5 and x < 10)|


```python
name = input("이름: ")
```

    이름: 홍길동
    


```python
# 사용자가 입력한 이름이 전종민이니?
name == "전종민"
```




    False




```python
age = input("나이: ")
age = int(age)  # 문자열을 정수로 변환
```

    나이: 30
    


```python
# 사용자가 입력한 나이가 20세 이상인가?
age >= 20
```




    True




```python
# 나이가 20대인가?
age >= 20 and age < 30
```




    False




```python
(age >= 20) & (age < 30)
```




    False




```python
# 나이가 20대가 아닌가?
age < 20 or age >= 30
```




    True




```python
not(age >= 20 and age < 30)
```




    True




```python
True ^ True
```




    False




```python
False ^ False
```




    False




```python
True ^ False
```




    True



<b style='font-size:1.2em'>조건 연산자</b>  ```(조건문이 아님)```


True일때 결과값 <b style='color:purple'>if</b> 조건식 <b style='color:purple'>else</b> False일때 결과값
- 조건식이 True이면 앞의 값을 False이면 뒤의 값을 연산결과로 반환한다.


```python
num = int(input("정수: "))
```

    정수: 0
    


```python
"양수" if num >= 0 else "음수"
```




    '양수'




```python
"양수" if num > 0 else "0" if num == 0 else "음수"
```




    '0'




```python
a = 10
```

## 문자열 (string)

- 0글자 이상의 문자열을 표현한다.
- 파이썬 3.0 부터는 유니코드 문자열을 지원하므로 영문자 뿐 아니라 모든 나라의 철자들을 기본으로 사용할 수 있다.
- 문자열 표현식
    - **작은 따옴표 또는 큰 따옴표**로 감싼다.
    - 여러줄 문자열(Multiline string)은 **3개 짜리 작은따옴표 또는 큰따옴표**로 감싼다.
        - 문자열 데이터에 `엔터`가 들어갈 경우 편리하다.
    - Escape 문자
        - 키보드에는 있지만 글자로 표현할 수 없는 문자들을 표현할 때 사용한다. `예) 엔터, Tab, Back space 등`
        - 사용하는 글자가 원래 의미에서 벗어나(escape) 다른 의미로 쓰인다고 해서 escape문자라고 한다.
        - 파이썬 뿐 아니라 모든 프로그래밍 언어에서 사용하는 표준이다.
        - 표현: `\문자` 
  


```python
a = '''안녕하세요
저는 전종민입니다.'''

print(a)
a
```

    안녕하세요
    저는 전종민입니다.
    




    '안녕하세요\n저는 전종민입니다.'



      
        
<b style='font-size:1.2em'>주요 Excape 문자</b>

|Escape문자|설명|
|-|-|
|\n|엔터|
|\t|Tab|
|\b|Backspace|
|\\\\|\|
|\\\"|"|
|\\\'|'|


>- r-string (raw string)
>  - 문자열 앞에 r 접두어를 붙인다. (raw) 
>  - escape 문자구분자인 \를 무시하여 escape 문자로 변환하지 않고 작성한 그대로 사용한다.
>  - ex) r"c:\test\example\a.txt"
        


```python
a2 = "안녕하세요.\n저는 전종민입니다."
print(a2)
```

    안녕하세요.
    저는 전종민입니다.
    


```python
print('a\tb')
print('a\nb')
print('가나다\b라')
```

    a	b
    a
    b
    가나다라
    


```python
print('c:\test\n_count')
print('c:\\test\\n_count')
print(r'c:\test\n_count')  # raw-string: escape 문자 '\'를 무시하고 한 글자로 취급
print("a\"b", 'a"b')
print('가\'나', "가'나")
print('가"나\'다', '''가"나'다''')
```

    c:	est
    _count
    c:\test\n_count
    c:\test\n_count
    a"b a"b
    가'나 가'나
    가"나'다 가"나'다
    

**문자열 크기 비교**
1. 같은 종류(한글끼리, 숫자끼리, 소문자끼리...): 사전식배열, 뒤에 나오는 것이 앞에 나오는 것보다 크다
2. 다른 종류(한글과 소문자, 숫자와 한글): 특수문자 < 숫자 < 대문자 < 소문자 < 한글


```python
"가" < "나" # 유니코드를 바탕으로 바교 사전 식 비교
```




    True




```python
"A" < "가"
```




    True




```python
"A" < "a"
```




    True




```python
"ab가" < "ab나"  # (= "가"와 "나" 비교)
```

<b style='font-size:1.2em'>문자열 연산자</b>
- 문자열 + 문자열
    - 두 문자열을 합친다.
    - 문자열은 문자열과만 `+` 연산을 할 수 있다. 다른 타입과 합칠 경우 다른 타입을 문자열로 변환한 뒤 연산해야 한다. (str() 함수이용)


```python
name = "홍길동"
print("이름:", name)
age = 20
# print("나이:", 20) # 문자열 + 정수 (X)
print("나이:", str(20)) # 나이 + 20
```

    이름: 홍길동
    나이: 20
    

- 문자열 * 정수
    - 문자열을 정수번 반복해서 합친다.


```python
print("안녕" * 4)
```

    안녕안녕안녕안녕
    


```python
print("정보1")
print("-"*100)
print("정보2")
```

    정보1
    ----------------------------------------------------------------------------------------------------
    정보2
    

- `in`, `not in`
    - 문자열A in 문자열B
        - 문자열A가 문자열B에 **있**으면 True, 없으면 False를 반환
    - 문자열A not in 문자열B
        - 문자열A가 문자열B에 **없**으면 True, 있으면 False를 반환


```python
a = "hello world"

print("hello" in a)
print("hello" not in a)
```

    True
    False
    


```python
address = "서울시 서초구 서초동\n"
print("서초구" in address)
print("동작구" in address)
```

    True
    False
    

- len(문자열)
    - 글자수를 반환한다.


```python
len(address)
```




    12



### Indexing과 Slicing

- Indexer 연산자
    - `집합형태[식별자]`
        - 여러개의 값이 모여있는 집합 형태의 데이터에서 그 중 일부를 조회할 때 사용하는 연산자.
            - 문자열, 자료구조 등 다양한 데이터타입에 사용한다.
        - 조회하고자 하는 일부를 식별할 수 있는 `식별자`를 \[\] 안에 넣어 조회한다.
- indexing과 slicing
    - **indexing**: 집합내에서 하나의 값을 조회하는 방법
    - **slicing**: 집합내에서 여러개의 값들을 범위로 지정해 조회하는 방법

### Indexing과 Slicing을 이용해 문자열내의 일부 문자들(sub string) 조회
- **문자열 내의 각 문자들은 식별자로 index를 가진다.**
    - 양수 index
        - 문자열 앞에서 부터 붙여주는 index
        - 0부터 1씩 증가하는 값을 붙여준다.
        - **앞에서 몇번째 글자 식**으로 조회할 때 사용한다.
    - 음수 index
        - 문자열 맨 뒤에서 부터 붙여주는 index
        - -1 에서 1씩 감소하는 값을 붙여준다.
        - **뒤에서 몇번째 글자 식**으로 조회할 때 사용한다.
    - 모든 문자는 양수/음수 index 두개를 가진다.
    ![index](/images/ch02_01.png)

#### Indexing
- 문자열\[index\]
    - index의 문자를 조회
    - 변경은 안된다.
        - 문자열 값 안의 일부를 변경할 수 없다.
        - 문자열처럼 내부의 값을 변경할 수 없는 데이터 타입을 불변(Immutable)이라고 한다. 


```python
s = "안녕하세요. 반갑습니다."
print("글자수:", len(s))
```

    글자수: 13
    


```python
print("앞에서 두번째 글자:", s[2-1])
```

    앞에서 두번째 글자: 녕
    


```python
print("앞에서 7번째 글자:", s[6])
```

    앞에서 7번째 글자:  
    


```python
print("뒤에서 3번째 글자:", s[-3], s[10])
print("뒤에서 4번째 글자:", s[-4])
```

    뒤에서 3번째 글자: 니 니
    뒤에서 4번째 글자: 습
    

#### Slicing
- 기본구문: **문자열 \[ 시작 index : 종료 index : 간격\]**
    - 시작 index ~ (종료 index – 1)
    - 간격을 지정하면 간격만큼 index를 증/감한다. (생략 시 1이 기본 간격)
- **0번 index 부터 조회 할 경우 시작 index는 생략가능**
    - str_value \[ : 5\] => 0 ~ 4 까지 조회
- **마지막 index까지 (끝까지) 조회 할 경우 종료 index는 생략 가능**
    - str_value\[2 : \] => 2번 index 에서 끝까지
- **명시적으로 간격을 줄 경우**
    - str_value\[ : : 3 \] => 0, 3, 6, 9.. index의 값 조회
    - str_value\[1 : 9 : 2\] => 1, 3, 5, 7 index의 값 조회
- **시작 index > 종료 index, 간격을 음수로 하면 역으로 반환한다.(Reverse)**
    - str_value\[5: 1: -1\] => 5, 4, 3, 2 index의 값 조회
    - str_value\[: : -1\]  => 마지막 index ~ 0번 index 까지 의미. Reverse 한다.


```python
s2 = '0123456789'
```


```python
print(s2[2:7]) # 2 ~ 7-1, 간격: 1
print(s2[0:7:2]) # 0 ~ 7-1, 간격: 2
print(s2[:7:2])
print(s2[2:len(s2)]) # 2 ~ 끝까지, 간격: 1
print(s2[2:])
print(s2[::3]) # 0 ~ 끝까지, 간격: 3
print(s2[7:2:-1]) #reverse
print(s2[::-1])
```

    23456
    0246
    0246
    23456789
    23456789
    0369
    76543
    9876543210
    

### Format string (형식문자열) 생성
- 문자열에 문장 형식/구성/Layout을  미리 만들어 놓고 값은 나중에 대입하는 방식으로 문자열을 만드는 것
    - 여러 문자열이 같은 Layer에 특정 값들만 바뀌는 경우 사용한다.
        - 이름 : XXX 나이 : XXX 성별 : XXX  
        - 기본 형식은 같은데 XXX에 들어갈 값들은 그때 그때 다를 경우 사용
1. format() 함수 이용
    - 문자열을 만들 때 값을 나중에 넣을 위치 { } 로 표시하고 format() 메소드에서 { }에 들어갈 값을 순서대로 넣는다.

> 값을 넣어줄 자리를 지정하는 것을 **placeholder** 라고 한다.


```python
name = "홍길동"
age = 20
address = "서울"

# 이름: "홍길동"
# 나이: 20
# address: "서울"

info = "이름: " + name + "\n나이: " + str(age) + "\n주소: " + address
print(info)
```

    이름: 홍길동
    나이: 20
    주소: 서울
    


```python
layout = "이름: {}\n나이: {}\n주소: {}"
print(layout)
info = layout.format(name, age, address)
print(info)
```

    이름: {}
    나이: {}
    주소: {}
    이름: 홍길동
    나이: 20
    주소: 서울
    


```python
print(layout.format("이순신", 15, "인천"))
```

    이름: 이순신
    나이: 15
    주소: 인천
    


```python
info2 = "이름: {}\n나이: {}\n주소: {}".format(name, age, address) # 요즘은 이것보다 fstring을 사용함
print(info2)
```

    이름: 홍길동
    나이: 20
    주소: 서울
    


```python
layout2 = "제 이름은 {}이고 나이는 {}세 입니다. 저는 {}에 살고 있습니다. 제일 친한 친구는 {}으로 저와 이름이 같습니다."
txt = layout2.format(name, age, address, name)
print(txt)
```

    제 이름은 홍길동이고 나이는 20세 입니다. 저는 서울에 살고 있습니다. 제일 친한 친구는 홍길동으로 저와 이름이 같습니다.
    

- 자주 안쓰는 방식


```python
# 동일한 값을 여러 placeholder에 넣을 경우 format()에 전달하는 값의 순서를 넣어준다.
layout3 = "제 이름은 {0}이고 나이는 {1}세 입니다. 저는 {2}에 살고 있습니다. 제일 친한 친구는 {0}으로 저와 이름이 같습니다."
txt2 = layout3.format(name, age, address)
print(txt2)
```

    제 이름은 홍길동이고 나이는 20세 입니다. 저는 서울에 살고 있습니다. 제일 친한 친구는 홍길동으로 저와 이름이 같습니다.
    


```python
# placeholder에 이름을 설정.
layout4 = "제 이름은 {name}이고 나이는 {age}세 입니다. 저는 {addr}에 살고 있습니다. 제일 친한 친구는 {name}으로 저와 이름이 같습니다."
txt3 = layout4.format(name = name, age = age, addr = address)
print(txt3)
```

    제 이름은 홍길동이고 나이는 20세 입니다. 저는 서울에 살고 있습니다. 제일 친한 친구는 홍길동으로 저와 이름이 같습니다.
    

2. % value 사용
    - 타입을 지정하는 % value를 이용해 값을 넣어줄 자리를 지정한다.
    - format 문자열과 넣어줄 값은 % 로 구분한다.
    
|% value|설명|
|-|-|
|%s|string (모든 값을 넣을 수 있다)|
|%d|int-정수|
|%f|float-실수|
|%%|%|

실수는 소수점자릿수를 6자리로 맞추기 때문에 정밀도를 표현하는 표현식을 지정하는 것이 좋다. `ex) %.2f`


```python
name = "홍길동"
age = 20
tall = 185.23
bmi = 23
```


```python
info = "이름: %s, 나이: %d, 키: %.2f, BMI: %d%%" %(name, age, tall, bmi)
print(info)
```

    이름: 홍길동, 나이: 20, 키: 185.23, BMI: 23%
    

3. f-string (format string)
    - 파이썬 3.6에서 추가된 형식
    - 문자열 앞에 접두어 `f`를 사용한다.
    - 값을 넣을 자리에 {변수명} 을 이용해 변수가 가진 값을 문자열에 추가한다.


```python
info4 = f"이름: {name}, 나이: {age}, 키: {tall}, BMI: {bmi}%"
print(info4)
```

    이름: 홍길동, 나이: 20, 키: 185.23, BMI: 23%
    

### string 주요 메소드
- 메소드: 특정한 타입에만 적용되는 함수 ex) 문자열에서만 쓸 수 있는 함수, 사용법 ```"문자열".함수()```

|메소드|설명|
|-|-|
|split(구분문자열)|구분 문자열을 기준으로 나눈다.|
|strip(), lstrip(), rstrip()|앞뒤(strip) 앞(lstrip) 뒤(rstrip) 공백 제거|
|replace('바꿀 문자열', '새문자열')|바꿀 문자열을 새문자열로 변경|
|count('세려는 문자열')|string안에 세려는 문자열이 몇개 있는지 반환|
|index(문자열), find(문자열)|문자열이 몇번째 index에 있는지 반환|
|upper(), lower()|모든 글자를 대문자(upper), 소문자(lower)로 변환|
|capitalize()|문자열의 시작 글자를 대문자로 변환|
|islower(), isupper()|문자열이 모두 소문자(islower), 대문자(isupper)이면 True 아니면 False를 반환|
|startswith("문자열"), endswith("문자열")|문자열로 시작하는지/끝나는지 여부 반환|


```python
s = "컴퓨터 램 모니터 GPU"
result = s.split()   # 처리결과를 리스트(list)에 담아서 반환.
print(result)
```

    ['컴퓨터', '램', '모니터', 'GPU']
    


```python
s = "컴퓨터|램|모니터|GPU"  # 구분자: |
result = s.split('|')   # 기본 구분자 -> 공백, 공백이외의 문자열일 경우 메소드에 전달해준다.
print(result)
```

    ['컴퓨터', '램', '모니터', 'GPU']
    


```python
id = "  abcde   "
print(len(id))
result = id.strip()
print(len(result))
result   # 공백이 없어지는 것을 보기 편하기 때문에 print(result) 대신 사용한다.
```

    10
    5
    




    'abcde'




```python
id.lstrip()
```




    'abcde   '




```python
s = "aaabbbcccdddeeeabcde"
result = s.replace('a', '에이')
print(s)
print(result)
```

    aaabbbcccdddeeeabcde
    에이에이에이bbbcccdddeee에이bcde
    


```python
result = s.replace('aaa', '에이')
print(result)
```

    에이bbbcccdddeeeabcde
    


```python
print("전체글자수:", len(s))
print("s에 a가 몇개? ", s.count('a'))
s.count('bb')
```

    전체글자수: 20
    s에 a가 몇개?  4
    




    1




```python
print(s.index('a'))   # 첫번째로 찾았을 때의 값
print(s.index('bb'))
#print(s.index('가')) # 찾는 값이 없으면 에러(Exception) 발생
```

    0
    3
    


```python
print(s.find('a'))
print(s.find('가'))   # 찾는 값이 없으면 -1을 반환.
"있음" if s.find('가') != -1 else "없음"
```

    0
    -1
    




    '없음'




```python
s = "my name is jack. i'm 20."
s2 = s.upper()
print(s2)
```

    MY NAME IS JACK. I'M 20.
    


```python
s3 = s2.lower()
print(s3)
```

    my name is jack. i'm 20.
    


```python
s4 = s3.capitalize()
print(s4)
```

    My name is jack. i'm 20.
    


```python
s.islower()
```




    True




```python
s2.isupper()
```




    True




```python
s4.islower()
```




    False




```python
s4.isupper()
```




    False




```python
s = "https://www.naver.com"
r1 = s.startswith("https://")
r2 = s.startswith("http://")
r3 = s.endswith(".com")
r4 = s.endswith(".go.kr")
print(r1, r2, r3, r4)
```

    True False True False
    

## 데이터 타입 변환 (형변환) 함수
- 여러타입을 바꿀 수 있기 때문에 함수라고 한다.
- 정수로 변환
    - int(value)
- 실수로 변환
    - float(value)
- 문자열로 변환
    - str(value)
- 논리형으로 변환
    - bool(value)


```python
print(int(3.56)) # float -> int (내림)
print(30 + int("20")) # str -> int
num = int(input("정수: "))
print(num + 50)
```

    3
    50
    정수: 100
    150
    


```python
print(float(3)) # int -> float
print(5 + float("4.2")) # 문자열 -> float
num = float(input("실수: "))
print(num + 10)  # 저장방식(floating point)이 엄청 큰 수를 저장할 수 있지만 저장할 수 없는 수가 있어서 계산이 정확하게 나오지 않을 수 있다. -> decimal
```

    3.0
    9.2
    실수: 10.56
    20.560000000000002
    


```python
# int("abc") # 정수형태의 문자열만 변환이 가능
# int("5.3")
int(5.3) # 실수에서 정수로 변환은 가능
```




    5




```python
# float("abc") # 실수형태의 문자열만 변환 가능
float("5")
```




    5.0




```python
print(int(True)) # 저장될 때 1로 저장
print(int(False)) # 저장될 때 0으로 저장
# True의 개수를 구하는 방법 True False 전부 더하기
```

    1
    0
    


```python
print("나이: " + str(30))  # int -> str
```




    '나이: 30'




```python
print(bool(10))
print(bool(-20))
print(bool(0))
print(bool(0.0))
```

    True
    True
    False
    False
    


```python
print(bool("a"))
print(bool("abc"))
print(bool(" "))
print(bool(""))
```

    True
    True
    True
    False
    


```python
bool(None)
```




    False



# TODO


```python
#1. 주민번호 "901211-1027213"의 앞 6자리만 조회해서 출력하시오.

num = "901211-1027213"
print(num[:6])
print(num.split("-")[0])
```

    901211
    901211
    


```python
#2. "안녕하세요" 를 10번 출력하시오.

print("안녕하세요"*10)
```

    안녕하세요안녕하세요안녕하세요안녕하세요안녕하세요안녕하세요안녕하세요안녕하세요안녕하세요안녕하세요
    


```python
#3. 다음 문자열의 글자수를 출력하시오.
str_value = "akdlclkdkdlelql39du7마구0ㅌ" 

print(len(str_value))
```

    24
    


```python
#4.
name="TV"
price=300000
maker = "LG"
# 위 변수의 값을 다음과 같은 형태로 출력하시오.
#"제품명 : TV, 가격 : 300000, 제조사 : LG"

print("제품명 : "+name+", 가격 : "+str(price)+", 제조사 : "+maker)
print("제품명 : {}, 가격 : {}, 제조사 : {}".format(name, price, maker))
print("제품명 : %s, 가격 : %d, 제조사 : %s" %(name, price, maker))
print(f"제품명 : {name}, 가격 : {price}, 제조사 : {maker}")
```

    제품명 : TV, 가격 : 300000, 제조사 : LG
    제품명 : TV, 가격 : 300000, 제조사 : LG
    제품명 : TV, 가격 : 300000, 제조사 : LG
    제품명 : TV, 가격 : 300000, 제조사 : LG
    


```python
#5.
fruits = "사과 복숭아 귤 배"
# 위 fruits에 "수박"이 있는지 확인하는 코드를 작성하시오.

print("수박" in fruits)

print("수박 있음" if "수박" in fruits else "수박 없음")
```

    False
    수박 없음
    


```python
#6.
str_value="aldkjaldjfalfjlksajfladlkaalalkdjfa"
# str_value 문자열안에 a가 몇개 있는지 출력하시오.

print(str_value.count('a'))
```

    9
    
