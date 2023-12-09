# Composition over inheritance
- Effective java item 18
- GoF Design patterns 1.6

- Composition 을 번역하면 복합이라고 하는데 와닿지 않는 단어다.
- 코드의 재사용을 위해 inheritance 보다 composition 이 더 낫다는 이야기이다. 두 책에 모두 나와있다.
- 코드를 재사용 하기 위해 클래스에 기능을 넣고 이를 extends 하거나, 또는 필드에 두고 쓰는 방법이 있는데 이 중 후자가 더 낫다는 뜻이다.

### Delegation
- 이를 Delegation 이라고 하는데, 이는 gof 에서 디자인 패턴으로 분류되지 않는다. (패턴 카탈로그에 없다.)
- Delegation 을 사용하는 디자인 패턴에는 state, strategy, visitor, mediator, 책임 연쇄, bridge 패턴이 있다.

### Others
- 코드를 재사용 하기 위한 방법에는 1. inheritance 2. composition 3. generics 가 있다.
