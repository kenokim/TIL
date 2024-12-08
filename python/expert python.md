## ch1.
### python - interpreted language
- runtime execution: python source code -> bytecode 로의 변환은 런타임에 일어나며, 이후 CPython 등의 인터프리터가 실행됩니다.
- 바이트코드는 PVM 에서 동작한다.

- 변수에 클래스를 저장하고 사용할 수 있다.
```python
class Hello:
  def __init__(self):
      print('Hello')

x = Hello
x()
```
