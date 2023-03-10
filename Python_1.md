# ⭐ Python - 파이썬 기초

> 컴퓨터는 저장(Remember)하고 조작(Calculation)하는 도구

> 프로그래밍: 명령어의 모음(집합)

> 컴퓨터 프로그래밍 언어: 컴퓨터에 명령하기 위한 약속


## 💡 파이썬(Python)이란?
- Easy to learn
  - 다른 프로그래밍 언어보다 문법이 간단하면서도 엄격하지 않음
    - 예시: 변수에 별도의 타입 지정이 필요 없음
  - 문법 표현이 매우 간결하여 프로그래밍 경험이 없어도 짧은 시간 내에 마스터 가능
    - 예시: 문장을 구분할 때 중괄호({,}) 대신 들여쓰기를 사용
- Expressive Language
  - 같은 작업에 대해서도 C나 자바로 작성할 때보다 더 간결하게 작성 가능
  ```java
  // 자바
  public class HelloPython {
    public static void main(string[] args) {
      system.out.println("Hello Python!");
    }
  }
  ```
  ```python
  # 파이썬
  print('Hello Python!')
  ```
- 크로스 플랫폼 언어
  - 윈도즈(Windows), macOS, 리눅스(Linux), 유닉스(Unix) 등 다양한 운영체제에서 실행 가능
- 인터프리터 언어(Interpreter)
  - 소스 코드를 기계어로 변환하는 컴파일 과정 없이 바로 실행 가능
  - 코드를 대화하듯 한 줄 입력하고 실행한 후 바로 확인할 수 있음
  ```
  2 + 2 # 사용자가 입력(input)  
  4     # 컴퓨터가 대답(output)
  ```
- 객체 지향 프로그래밍(Object Oriented Programming)
  - 파이썬은 객체지향 언어이며 모든 것이 객체로 구현되어 있음
    - 객체(Object): 숫자, 문자, 클래스 등 값을 가지고 있는 모든 것

## 💡 변수란?
- 컴퓨터 메모리 어딘가에 저장된 객체를 참조하기 위해 사용되는 이름
  - 객체(object): 숫자, 문자, 클래스 등 값을 가지고 있는 모든 것
  - 파이썬은 객체지향 언어이며, 모든 것이 객체로 구현되어 있음
- 동일 이름에 다른 객체를 언제든 할당할 수 있기 때문에 '변수'라고 불림
- 변수는 할당 연산자(=)를 통해 값을 할당(assignment)
- type()
  - 변수에 할당된 값의 타입
- id()
  - 변수에 할당된 값(객체)의 고유한 이이덴티티(identity) 값이며, 메모리 주소
- 변수 할당
  - 같은 값을 통시에 할당할 수 있음
    - 예시: x = y = 1004
  - 다른 값을 동시에 할당할 수 있음(multiple assignment)
    - 예시: x, y = 1, 2

## 💡 식별자(Identifiers)
- 파이썬 객체(변수, 함수, 모듈, 클래스 등)를 식별하는 데 사용하는 이름(name)
- 규칙
  - 식별자의 이름은 영문 알파벳, 언더스코어(_), 숫자로 구성
  - 첫 글자에 숫자가 올 수 없음
  - 길이 제한이 없고 대소문자를 구별
  - 다음의 키워드(keywords)는 예약어(reserved words)로 사용할 수 없음
    > False, None, True, and, as, assert, async, await, break, class, continue, def, del, elif, else, except, finally, for, from, global, if, import, in, is, lambda, nonlocal, not, or, pass, raise, return, try, while, with, yield
  - 내장함수나 모듈 등의 이름으로도 만들면 안 됨
    - 기존의 이름에 다른 값을 할당하게 되므로 더 이상 동작하지 않음

## 💡 객체의 종류
- 자료형(Data Type) 분류
  - 숫자
    - 수치형(Numeric Type)
      - 정수(int)
        - 모든 정수의 타입은 int
        - 오버플로우가 발생하지 않음
          - 오버플로우(overflow): 데이터 타입별로 사용할 수 있는 메모리의 크기를 넘어서는 상황
      - 실수(Float)
        - 정수가 아닌 모든 실수는 float 타입
        - 부동소수점에서 실수 연산 과정에서 발생 가능
      - 복소수(Complex)
        - 실수부와 허수부로 구성된 복소수는 모두 complex 타입
          - 허수부를 j로 표현
    - 불린형(Boolean Type)
      - True / False 값을 가진 타입은 bool
        - True는 1, False는 0에 해당함
      - 비교/논리 연산을 수행함에 있어서 활용됨
      - 다음은 모두 False로 변환
        - 0, 0.0, (), [], {}, "", None
    - 연산자(Operator)
      - 산술 연산자: 기본적인 사칙연산 및 수식 계산
        - \+ : 덧셈
        - \- : 뺄셈
        - \* : 곱셈
        - % : 나머지
        - / : 나눗셈
        - // : 몫
        - ** : 거듭제곱
      - 복합 연산자: 연산과 할당이 함께 이뤄짐
        - a += b : a = a + b
        - a -= b : a = a - b
        - a *= b : a = a * b
        - a /= b : a = a / b
        - a //= b : a = a // b
        - a %= b : a = a % b
        - a **= b : a = a ** b
      - 비교 연산자: 값을 비교하며 True / False 값을 리턴함
        - < : 미만
        - <= : 이하
        - \> : 초과
        - \>= : 이상
        - == : 같음
        - != : 같지 않음
        - is : 객체 아이덴티티
        - is not : 객체 아이덴티티가 아닌 경우
      - 논리 연산자: 논리식을 판단하여 참(True)과 거짓(False)을 반환함
        - and : 모두 참인 경우 참, 그렇지 않으면 거짓
        - or : 둘 중 하나라만 참이라도 참, 그렇지 않으면 거짓
        - not : 참, 거짓의 반대의 결과(True를 False로, False를 True로)
  - 시퀀스(Sequence)
    - 문자열(string): 문자들의 나열
    - 리스트(list): 변경 가능한 값들의 나열
    - 튜플(tuple): 변경 불가능한 값들의 나열
    - 레인지(range): 숫자의 나열
  - 컬렉션(Collection)
    - 세트(set): 중복 없는 유일한 값들의 모음
    - 딕셔너리(dictionary): 키-값들의 모음
  - None: 값이 없음을 표현하기 위한 None 타입
    - 일반적으로 반환 값이 없는 함수에서 사용하기도 함


## 💡 코드 작성 주의사항
- 대소문자 구분
- 띄어쓰기, 문장부호 등 주의 깊게 활용
- 들여쓰기(indent)
  - 문장을 구분할 때 들여쓰기를 사용
  - 들여쓰기를 할 때는 4칸(space 키 4번) 혹은 1탭(Tab 키 1번)을 입력
  - 한 코드 안에서는 반드시 한 종류의 들여쓰기를 사용

## 💡 주석(Comment)
- 코드에 대한 설명
  - 중요한 점이나 다시 확인하여야 하는 부분 표시
  - 컴퓨터는 주석을 인식하지 않으며 사용자를 위한 것임
- 주석으로 처리될 내용 앞에 '#'을 입력
  - 한 줄을 온전히 주석 처리하거나 코드 뒷부분에 주석을 덧붙일 수 있음
  - VS Code 단축키 : Ctrl + /

## 💡 사용자 입력
- input([prompt])
  - 사용자로부터 값을 즉시 입력받을 수 있는 내장함수
    - 대괄호 부분에 문자열을 넣으면 입력 시 해당 문자열을 출력할 수 있음
  - **반환 값은 항상 문자열의 형태로 반환**
- print()
  - 모니터 화면에 결과물을 출력하기 위해 사용
  - 변수의 경우 변수의 값을 출력하며 객체별 표현 방식에 따라 출력하게 됨

## 💡 실습 예제
- x = 10, y = 20 일 때, 각각 값을 바꿔서 저장하는 코드를 작성하시오.
  ```python
  # 방법 1) 임시변수 활용  
  tmp = x  
  x = y  
  y = tmp  
  print(x, y)
  ```
  ```python
  # 방법 2) Pythonic!  
  y, x = x, y  
  print(x, y)
  ```

## 💡 코드 스타일 가이드
- [PEP8](https://peps.python.org/pep-0008/)
- [구글 스타일 가이드](https://google.github.io/styleguide/pyguide.html)