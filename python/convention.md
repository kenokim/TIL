# PEP 8 convention
- PEP8: 파이썬 코드 스타일 가이드

## naming convention
- module: 'hello_module.py'
- class: 'HelloClass'
- function/method: 'hello_method()'
- non-public method: '__hello_method()'
- constant: 'HELLO_CONSTANT'

## expression & statement
- 컨테이너 or 시퀀스 검사: if list -> None 이거나 비어있으면 False 이다.
- 한 줄짜리 if/for/while/except 를 작성하지 말라.

## import
- module 을 import 할 경우 절대적인 이름을 사용하라.
- 표준 라이브러리 모듈, 서드 파티 모듈, 사용자 모듈 순서로 섹션을 나누고, 각 섹션은 알파벳 순으로 한다.

