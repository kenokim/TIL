## 파이썬 구조
- [Python Code] → [Interpreter] → [Bytecode] → [Virtual Machine (PVM)] → [CPU]

### GIL(Global Interpreter Lock)이란?
- GIL은 PVM 내부의 인터프리터 루프에 존재하는 전역 락입니다.
- 한 번에 하나의 스레드만 PVM에서 실행할 수 있도록 제한합니다.
- CPython 인터프리터의 특징이며, 다른 인터프리터(Pypy, Jython)에는 존재하지 않을 수 있습니다.

### GIL의 동작 방식
- PVM의 메인 인터프리터 루프(Interpreter Main Loop) 가 Bytecode를 하나씩 실행할 때, GIL을 획득해야 합니다.
- GIL은 스레드 간에 교대로 할당되며, 한 번에 하나의 스레드만 실행됩니다.
- GIL은 일정 시간이 지나면(Thread Switching Interval, 기본 약 5ms) 다른 스레드에 양보합니다.

### GIL 단점
- CPU 바운드 작업에서 GIL 때문에 멀티스레딩 성능이 낮으며, multiprocessing 이 권장된다.
- I/O 바운드 작업에서 GIL 의 영향은 크지 않다. -> 멀티스레딩을 할 수 있다.

## FastAPI
- asyncio 기반의 event loop 방식이다.
- Event loop 방식은 싱글스레드로, I/O 바운드 작업에 성능이 좋다.
