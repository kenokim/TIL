# Attribute
- Python에서 속성(attribute)은 객체(Object)의 특성이나 상태를 나타내는 값입니다. 속성은 객체 지향 프로그래밍의 기본 개념 중 하나로, 클래스(class) 내에 정의되어 객체가 가질 수 있는 데이터나 메서드를 포함합니다.
## 인스턴스 속성
- 객체가 생성될 때마다 독립적으로 갖게 되는 속성입니다.
```python
class Dog:
    def __init__(self, name, age):
        self.name = name  # 인스턴스 속성
        self.age = age    # 인스턴스 속성

my_dog = Dog("Buddy", 2)
print(my_dog.name)  # Buddy
print(my_dog.age)   # 2
```
## 클래스 속성
- 클래스 자체에 속하는 속성으로, 모든 인스턴스가 공유합니다.
```python
class Dog:
    species = "Canis familiaris"  # 클래스 속성

    def __init__(self, name, age):
        self.name = name  # 인스턴스 속성
        self.age = age    # 인스턴스 속성

my_dog = Dog("Buddy", 2)
print(my_dog.species)  # Canis familiaris
print(Dog.species)     # Canis familiaris
```
## 프로퍼티
- 특수한 속성으로, 게터(getter), 세터(setter) 메서드를 통해 속성의 값을 가져오거나 설정할 수 있습니다.
```python
class Dog:
    def __init__(self, name, age):
        self._name = name  # 이름 앞에 _를 붙여서 비공개 속성으로 만듦
        self._age = age    # 이름 앞에 _를 붙여서 비공개 속성으로 만듦

    @property
    def name(self):
        return self._name

    @name.setter
    def name(self, value):
        self._name = value

my_dog = Dog("Buddy", 2)
print(my_dog.name)  # Buddy
my_dog.name = "Max"
print(my_dog.name)  # Max
```
