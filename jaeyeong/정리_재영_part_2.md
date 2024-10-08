# 객체지향 바르게 이해하기 - 클래스

### 추상화를 통한 복잡성 극복

> 현상은 복잡하다. 현실은 단순하다. 버릴 게 무엇인지 알아내라. - 리처드 파인만

현실은 있는 그대로 모두 받아들이기에는 너무나 복잡하다. 이 지독하게 복잡한 현실 속에서 우리는 우리에게 필요한 본질들만 골라낼 수 있어야한다. 이 과정을 추상화라고 부른다.

추상화의 목적은 불필요한 부분을 무시함으로써 현실에 존재하는 복잡성을 극복하는 것이다. 그래서 추상화란 현실에서 출발하되 불필요한 부분을 도려내가면서 사물의 놀라운 본질을 드러나게 하는 과정이라고 할 수 있다.

훌륭한 추상화는 목적에 부합하는 것이어야한다. 추상화가 의도된 목적이 아닌 다른 목적으로 사용된다면 안하느니만 못하다. 추상화의 수준, 이익, 가치는 목적에 의존적이다.

추상화를 사용함으로써 우리는 극도로 복잡한 이 세상을 그나마 제어 가능한 수준으로 단순화 할 수 있는 것이다.

### 타입

데이터 타입은 메모리 안에 저장된 데이터의 종류를 분류하는 데 사용하는 메모리 집합에 관한 메타데이터다. **데이터에 대한 분류는 암시적으로 어떤 종류의 연산이 해당 데이터에 대해 수행될 수 있는지를 결정**한다.

데이터 타입에 대해 정의한 이유는 전통적인 데이터 타입과 객체지향의 타입 사이에 깊은 연관성이 있기 때문이다. 객체를 타입에 따라 분류하고 그 타입에 이름을 붙이는 것은 결국 프로그램에서 사용할 새로운 데이터 타입을 선언하는 것과 같다.

전통적인 데이터 타입의 개념은 객체의 타입에도 그대로 적용된다.

1. 어떤 객체가 어떤 타입에 속하는지를 결정하는 것은 객체가 수행하는 행동이다. 동일한 행동을 수행할 수 있다면 동일한 타입으로 분류될 수 있다.
2. 객체의 내부적인 표현은 외부로부터 철저하게 감춰진다.

**객체의 내부 표현 방식이 다르더라도 어떤 객체들이 동일하게 행동한다면 그 객체들은 동일한 타입에 속한다.** 결과적으로 동일한 책임을 수행하는 일련의 객체는 동일한 타입에 속한다고 말할 수 있다.

이로서 우리는 객체를 타입으로 분류할 때 사용해야 하는 명확한 기준을 깨달았다. 어떤 객체가 타입에 속한 다른 객체와 동일한 행동을 한다면 동일한 타입으로 분류할 수 있다. 다른 행동을 한다면 그 객체들은 서로 다른 타입으로 분류돼야 한다.

**결론적으로 객체의 타입을 결정하는 것은 객체의 행동뿐이다.**

여기서 객체지향의 다형성의 의미를 알 수 있다. 동일한 행동을 하는 동일한 타입에 속한 객체는 내부의 데이터 표현 방식이 다르더라도 동일한 메시지를 수신하고 이를 처리할 수 있다. 다만 메시지를 처리하는 내부의 구체적인 방식은 다를 수 있는 것이다.

그래서 훌륭한 객체지향 설계는 외부에 행동만을 제공하고 데이터는 행동 뒤로 감춰야 한다. 이 원칙을 캡슐화라고 부른다. 데이터가 캡슐의 벽을 뚫고 객체의 인터페이스를 오염시키는 순간 객체의 분류 체계는 급격히 위험에 노출되고 결과적으로 유연하지 못한 설계를 낳는다.

객체를 디자인하기 위해서는 데이터가 아니라 행동을 먼저 생각해야 한다.

1. 객체가 외부에 제공해야 하는 책임을 먼저 결정하고
2. 그 책임을 수행하는 데 적합한 데이터를 결정한 후
3. 데이터를 책임을 수행하는 데 필요한 외부 인터페이스 뒤로 캡슐화해야 한다.

**데이터를 먼저 결정하고 객체의 책임을 결정하는 방법은 유연하지 못한 설계라는 악몽을 초래한다.**

### 일반화/특수화(슈퍼타입/서브타입) 관계

일반적인 타입이란 특수한 타입이 가진 모든 행동들 중에서 일부 행동만을 가지는 타입을 가리킨다. 특수한 타입이란 일반적인 타입이 가진 모든 행동을 포함하지만 거기에 더해 자신만의 행동을 추가하는 타입을 가리킨다.

여기서 중요한 것은 객체지향에서 일반화/특수화 관계를 결정하는 것은 객체의 상태를 표현하는 데이터가 아니라 행동이라는 것이다.

좀 더 일반적인 타입을 슈퍼타입, 좀 더 특수한 타입을 서브타입이라고 한다. 다시 한 번 강조하지만 한 타입이 다른 타입의 슈퍼, 서브 타입이 되도록 하는 것은 행동이다.

일반적으로 서브타입은 슈퍼타입을 대체할 수 있어야 한다. 따라서 어떤 타입을 다른 타입의 서브타입이라고 말할 수 있으려면 다른 타입을 대체할 수 있어야 한다. → 리스코프 치환 원칙 (Liskov Substitution Principle)

> 서브타입이 슈퍼타입의 행동을 조금이라도 수정하면 그것은 잘못된 설계일까?

### 클래스

타입을 구현하는 가장 보편적인 방법은 클래스를 이용하는 것이다. '타입을 구현한다’는 말은 클래스와 타입은 동일하지 않다는 말이다. **클래스는 단지 타입을 구현할 수 있는 여러 구현 메커니즘 중 하나일 뿐**이다. JS와 같은 프로토타입 기반의 언어에는 클래스가 존재하지 않는다.

객체지향 패러다임을 주도하는 대부분의 프로그래밍 언어는 클래스를 기반으로 하기 때문에 대부분의 사람들은 클래스와 타입을 동일한 개념이라고 생각한다.

객체를 분류하기 위해 타입을 결정해야 하는데, 프로그래밍 언어를 이용해 타입을 구현할 수 있는 한 가지 방법이 클래스라는 사실을 아는 것 만으로도 충분하다.

**클래스는 타입을 구현하기 위해 프로그래밍 언어에서 제공하는 구현 메커니즘이라는 사실을 기억하라.**

### 협력

객체의 모양을 빚는 것은 객체가 참여하는 협력이다. 어떤 협력에 참여하는지가 객체에 필요한 행동을 결정하고, 필요한 행동이 객체의 상태를 결정한다. 개별적인 객체의 행동이나 상태가 아니라 객체들 간의 협력에 집중하라.

협력은 한 사람이 다른 사람에게 도움을 요청할 때 시작된다. 자신의 일을 처리하던 중 자신의 힘으로 해결하기 어려운 문제에 부딪히게 되면 도움을 줄 수 있는 누군가에게 도움을 요청한다. 요청을 받은 사람 역시 마찬가지로 다른 누군가에게 도움을 요청할 수 있다. 결과적으로 협력은 다수의 요청과 응답으로 구성 된 여러 흐름이다.

그리고 **요청과 응답은 협력에 참여하는 객체가 수행할 책임을 정의**한다.

### 책임

> **명확한 책임이 애플리케이션의 미래를 결정짓는다.**

어떤 객체가 어떤 요청에 대해 응답해 줄 수 있거나, 적절한 행동을 할 의무가 있는 경우 해당 객체가 책임을 가진다고 말한다.

책임은 객체에 의해 정의되는 응집도 있는 행위의 집합으로, 객체가 알아야 하는 정보와 객체가 수행할 수 있는 행위에 대해 개략적으로 서술한 문장이다.

즉, 책임은 객체의 외부에 제공해 줄 수 있는 정보와 제공해줄 수 있는 서비스의 목록이다. 따라서 책임은 객체의 공용 인터페이스(public interface)를 구성한다.

책임은 객체지향 설계의 품질을 결정하는 가장 중요한 요소다. 객체지향 설계의 예술은 적절한 객체에게 적절한 책임을 할당하는 데 있다.

> 책임을 얼마나 잘게 혹은 얼마나 크게 나눠야 할지도 굉장히 어려운 문제로 보인다.

### 역할

**역할은 책임의 집합**을 간단하게 정의한 것이다. 그래서 역할은 협력 내에서 한 객체를 다른 객체로 대체할 수 있음을 나타내는 일종의 표식이다. 그리고 이말인 즉슨 역할을 대체할 수 있는 객체는 동일한 메시지를 이해할 수 있는 객체라는 말이다.

동일한 역할을 수행하는 객체들이 동일한 메시지를 수신할 수 있기 때문에 동일한 책임을 수행할 수 있다는 것은 매우 중요한 개념이다. 이를 제대로 이해해야만 객체지향이 제공하는 많은 장점을 누릴 수 있다.

역할의 개념을 사용하면 유사한 협력을 추상화할 수 있다. 위에서 책임은 객체의 공용 인터페이스를 구성한다고 했다. 그 이유가 여기에 있다. 유사한 협력을 역할로 추상화 한 것이 공용 인터페이스이다.

인터페이스로 협력이 유연해지며 다양한 객체들이 동일한 협력에 참여할 수 있기 때문에 재사용성이 높아진다.

객체들이 동일한 역할을 대체하기 위해서는 해당 역할이 수행하는 모든 책임을 동일하게 수행할 수 있어야 한다.

> 객체지향의 핵심은 클래스를 어떻게 구현할 것인가가 아니라 객체가 협력 안에서 어떤 책임을 갖고 어떤 역할을 수행할 것인지를 결정하는 것이다.

### 너무 추상적인 책임

포괄적이고 추상적인 책임을 선택한다고 해서 무조건 좋은 것은 아니다. 책임이 수행 방법을 제한할 정도로 너무 구체적인 것도 문제지만 협력의 의도를 명확하게 표현하지 못할 정도로 추상적인 것 역시 문제다.

책임은 협력에 참여하는 의도를 명확하게 설명할 수 있는 수준 안에서 추상적이어야 한다.

### 테스트 주도 개발 (Test-Driven-Development)

테스트 주도 개발(이하 TDD)는 좋은 객체지향 설계에 대한 깊은 고민에서 나온 개발 방법론이다. 객체지향에 대한 이해가 부족한 상태에서 TDD 의 개념을 접하면 잘 와닿지가 않는다. TDD 는 개발 속도를 느리게 하는 그저 번거로운 장치로 보이기 쉽다. 하지만 객체지향의 핵심을 이해하고 책임과 협력의 관점에서 객체를 바라보고 TDD 를 이해해보자. TDD 의 진짜 의미를 이해할 수 있을 것이다.

TDD 의 기본적인 틀은 테스트 코드를 작성하고, 테스트를 통과하는 코드를 작성한 후 리팩토링하는 과정이다. 이 간단한 흐름은 **우리가 객체의 책임을 먼저 생각하고 구현을 그 뒤에 하도록 강제한다.** 우리가 앞서 말했던 좋은 객체지향 설계를 강제하는 것이다!

테스트를 작성하기 위해 객체의 메서드를 호출하고 반환값을 검증하는 것은 객체가 수행해야 하는 책임에 관해 생각한 것이다. 그 과정에서 stub, mock 객체를 사용하는 것은 객체와 협력하는 대상에 대해 고민한 결과를 코드로 표현한 것이다.

객체의 역할, 책임, 협력에 집중하고 객체지향의 원칙을 적용하려는 깊이 있는 고민과 노력을 통해서만 TDD 의 혜택을 누릴 수 있다.

