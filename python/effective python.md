## 파이썬 용어
### 프로젝트
my_project/
├── my_package/
│   ├── __init__.py
│   ├── module1.py
│   └── module2.py
├── tests/
│   ├── test_module1.py
│   └── test_module2.py
├── setup.py
├── requirements.txt
├── README.md
└── .gitignore
### 패키지
- 폴더로 구분되는 __init__ 을 포함한 것

### 모듈
- .py 로 저장되는 단일 스크립트

### 라이브러리
- 함수, 클래스, 모듈 등의 집합으로 논리적 개념
- 패키지, 모듈은 물리적 개념

## ch1. pythonic python programming
### 1. 파이썬 버전
- 현재 3.10, 3.11 이 가장 많이 사용되며, 3.11 에서는 새로운 global interpreter lock (GIL) 관리, 인터프리터 최적화로 인해 성능이 향상(10~60%) 되었다.
  - 성능 향상이란, 연산 작업 속도 개선, 더 적은 메모리 사용, 동시성 개선, 예외처리 속도 개선 등이 포함된다.
  - cf). JAVA 에서의 성능 향상: 자료구조 사용, JVM 튜닝 (옵션, GC 선택), 메모리 관리 최적화 (string buffer, string builder), 멀티스레딩, 비동기 처리, 프로파일링 툴을 활용하여 디버깅

## ch10. 협업
### 82. community module
- PyPI 는 python package index 로 파이썬 커뮤니티에서 만든 모듈의 공통 패키지 저장소이다.
- pip 을 통해 여기서 package 를 설치하고 사용할 수 있다. (cli-tool)


