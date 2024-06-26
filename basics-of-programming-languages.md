# Basics of programming languages

## 변수 (Variable)

- 프로그램 실행 중 값을 저장하고 참조하기 위한 메모리 공간의 이름
- 변수를 통해 데이터를 저장, 조작, 관리함

## 자료형 (Data Type)

- 변수에 저장할 수 있는 데이터의 유형을 정의함
- 정수형, 실수형, 문자열 등 다양한 자료형이 존재하며, 자료형에 따라 메모리 할당 방식과 가능한 연산이 달라짐

## 리터럴 (Literal)

- 소스 코드 내에서 직접 표현한 값 자체를 의미함
- 숫자, 문자, 문자열 등이 리터럴에 해당하며, 변수와 달리 고정된 값을 나타냄

## 연산자 (Operator)

- 변수나 리터럴에 대해 연산을 수행하는 기호
- 산술, 비교, 논리 연산 등 다양한 연산자를 통해 데이터를 처리하고 프로그램의 흐름을 제어함

## 제어 구조 (Control Structure)

- 프로그램의 실행 순서를 제어하는 구문
- 조건문(if, switch)과 반복문(for, while)을 사용하여 로직을 구현하고 실행 흐름을 변경함

## 함수 (Function)

- 특정 작업을 수행하는 코드의 집합
- 입력값을 받아 처리하고 결과를 반환하며, 코드의 재사용성과 모듈화를 높임

## 재귀 함수 (Recursive Function)

- 함수 내에서 자기 자신을 호출하는 함수
- 반복적인 문제 해결에 유용하나, 잘못 구현할 경우 스택 오버플로우를 유발할 수 있음

## 배열 (Array)

- 같은 자료형의 데이터를 연속된 메모리 공간에 저장하는 자료구조
- 인덱스를 사용하여 배열 요소에 접근할 수 있으며, 데이터를 효율적으로 관리하고 처리할 때 사용함

## [객체 (Object)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/object.md)

- 데이터(속성)와 그 데이터에 관련된 동작(메서드)을 모아 둔 것
- 객체 지향 프로그래밍의 기본 단위로, 현실 세계의 개체를 모델링하는 데 사용됨

## [클래스 (Class)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/class.md)

- 객체를 생성하기 위한 템플릿이나 청사진
- 객체가 가져야 할 속성과 메서드를 정의하며, 클래스를 바탕으로 다양한 객체를 생성할 수 있음

## [접근 제어자 (Access Modifier)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/access-modifier.md)

- 클래스 내부의 멤버(속성과 메서드)에 대한 접근 권한을 제어하는 키워드
- public, private, protected 등을 통해 정보 은닉과 캡슐화를 구현하여 코드의 안전성을 높임

## [캡슐화 (Encapsulation)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/encapsulation.md)

- 객체의 내부 구현 세부 사항을 외부로부터 감추고, 정의된 인터페이스를 통해서만 접근을 허용하는 개념  
- 코드의 복잡성을 줄이고 유지보수성을 높이며, 시스템의 안정성을 향상시키는 객체 지향 프로그래밍의 중요한 원칙 중 하나

## [정보 은닉 (Information Hiding)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/information-hiding.md)

- 객체 내부의 구현 세부 사항을 외부에서 직접 접근할 수 없도록 제한하고, 정의된 인터페이스를 통해서만 상호작용하도록 하는 원칙
- 코드의 복잡성을 줄이고, 유지보수성을 높이며, 모듈 간의 결합도를 낮출 수 있음

## [상속 (Inheritance)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/inheritance.md)

- 기존 클래스의 속성과 메서드를 새로운 클래스에게 물려주는 객체 지향 프로그래밍의 개념
- 코드의 재사용성을 높이고, 클래스 간의 계층적 관계를 형성하는 데 유용함

## [오버라이딩 (Overriding)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/overriding.md)

- 상속받은 하위 클래스에서 상위 클래스의 메서드를 재정의하는 기법
- 하위 클래스에서 상위 클래스의 동작을 변경하거나 확장할 때 사용함

## [다형성 (Polymorphism)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/polymorphism.md)

- 동일한 메시지에 대해 객체의 타입에 따라 다르게 반응할 수 있는 능력
- 코드의 유연성을 높이고, 객체 지향 프로그래밍의 핵심 개념 중 하나임

## [오버로딩 (Overloading)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/overloading.md)

- 같은 이름의 메서드를 여러 개 정의하되, 매개변수의 타입이나 개수를 다르게 하여 다양한 동작을 수행하도록 하는 기법
- 동일한 메서드 이름으로 다양한 형태의 입력을 처리할 수 있음

## [추상화 (Abstraction)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/abstraction.md)

- 복잡한 시스템에서 핵심적인 개념이나 기능을 추출하여 간단한 인터페이스로 표현하는 기법
- 시스템의 복잡도를 관리하고 코드의 이해도를 높이는 데 도움이 됨

## [인터페이스 (Interface)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/interface.md)

- 클래스가 구현해야 할 메서드의 시그니처를 정의한 추상 타입
- 클래스 간의 상호작용 방식을 규정하고, 구현의 세부 사항을 숨김으로써 다형성을 실현하는 데 사용됨

## [추상 클래스 (Abstract Class)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/abstract-class.md)

- 추상 메서드를 포함하며, 직접 인스턴스를 생성할 수 없는 클래스
- 공통적인 기능을 하위 클래스에게 상속하고, 특정 메서드의 구현은 하위 클래스에 맡김

## [예외 처리 (Exception Handling)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/exception-handling.md)

- 프로그램 실행 도중 발생할 수 있는 예외 상황을 처리하는 기법
- 예외 발생 시 프로그램의 비정상 종료를 막고, 안정적인 동작을 보장할 수 있음

## [제네릭 (Generics)](https://github.com/cherrycoder9/cs-keywords/blob/main/basics-of-programming-languages/generics.md)

- 클래스나 메서드에서 사용할 데이터 타입을 나중에 지정할 수 있도록 매개변수화하는 기법
- 코드의 재사용성과 타입 안정성을 동시에 높일 수 있음

## 컬렉션 프레임워크 (Collection Framework)

- 다양한 자료구조를 구현한 클래스와 인터페이스의 모음
- 배열, 리스트, 맵 등 여러 형태의 데이터를 효율적으로 저장하고 관리할 수 있는 수단을 제공함

## 자료구조 (Data Structure)

- 데이터를 효율적으로 저장하고 조작하기 위한 데이터의 조직, 관리, 저장 형식
- 배열, 연결 리스트, 스택, 큐, 트리, 그래프 등 다양한 종류가 있으며, 상황에 따라 적절한 자료구조를 활용하는 것이 중요함

## 람다식 (Lambda Expression)

- 함수형 프로그래밍 패러다임을 지원하기 위해 도입된 익명 함수를 표현하는 방법
- 코드의 간결성과 가독성을 높이고, 함수를 변수에 할당하거나 인자로 전달할 수 있게 해줌

## 스트림 (Stream)

- 데이터의 흐름을 표현하는 추상화된 개념으로, 데이터 소스에서 추출된 연속된 요소들의 집합
- 중간 연산과 최종 연산을 통해 데이터를 처리하고, 파이프라인 형태로 연결하여 효율적인 데이터 처리를 가능케 함

## 포인터 (Pointer)

- 메모리 주소를 저장하는 변수로, 해당 주소에 저장된 데이터를 간접적으로 참조할 수 있게 해줌
- 동적 메모리 할당, 자료구조 구현 등에 활용되며, 잘못된 포인터 사용은 버그의 원인이 될 수 있음

## 스코프 (Scope)

- 변수, 상수, 함수 등의 식별자가 유효한 프로그램 영역
- 로컬 스코프, 글로벌 스코프 등이 있으며, 스코프를 적절히 관리하면 코드의 가독성과 유지보수성을 향상시킬 수 있음

## 상수 (Constant)

- 한번 값이 할당되면 변경할 수 없는 변수
- 코드의 가독성을 높이고, 실수로 값이 변경되는 것을 방지하는 데 도움이 됨

## 열거형 (Enumeration)

- 서로 관련된 상수들의 집합을 정의하는 데이터 타입
- 코드의 가독성을 높이고, 입력 오류를 방지하며, 타입 안정성을 보장하는 데 유용함

## 가비지 컬렉션 (Garbage Collection)

- 프로그램에서 더 이상 사용하지 않는 메모리를 자동으로 식별하고 해제하는 메모리 관리 기법
- 개발자가 직접 메모리를 관리하는 부담을 줄여주고, 메모리 누수 문제를 예방할 수 있음

## 네임스페이스 (Namespace)

- 식별자(변수, 함수, 클래스 등)를 논리적으로 그룹화하여 naming conflict를 방지하는 기능
- 대규모 프로젝트에서 코드를 모듈화하고 관리하는 데 효과적임

## 모듈 (Module)

- 관련된 코드를 하나의 파일이나 디렉토리로 구성한 독립적이고 재사용 가능한 소프트웨어 컴포넌트
- 코드의 가독성, 유지보수성, 재사용성을 높이고, naming conflict를 방지하는 데 도움이 됨

## 라이브러리 (Library)

- 특정 기능을 수행하는 모듈, 패키지, 함수의 집합체
- 검증되고 최적화된 코드를 재사용함으로써 개발 효율성과 코드 품질을 높일 수 있음

## API (Application Programming Interface)

- 프로그램 간 상호작용을 위해 사용되는 함수, 프로토콜, 도구의 집합
- 모듈화된 개발을 가능하게 하고, 소프트웨어 컴포넌트 간 통신을 용이하게 함

## 커링 (Currying)

- 다중 인자를 받는 함수를 단일 인자를 받는 함수의 시퀀스로 변환하는 기법
- 부분 적용 함수를 생성하여 코드의 재사용성과 가독성을 높이는 데 유용함

## 클로저 (Closure)

- 함수와 그 함수가 선언된 렉시컬 환경의 조합
- 함수가 선언된 환경의 변수를 캡슐화하여 해당 환경 밖에서도 상태를 유지할 수 있게 해줌

## 익명 함수 (Anonymous Function)

- 이름이 없는 함수로, 함수 리터럴이라고도 불림
- 주로 콜백 함수나 고차 함수에서 인라인으로 사용되며, 코드의 간결성을 높일 수 있음

## 매크로 (Macro)

- 컴파일 시점에 코드를 생성하거나 변형할 수 있는 기능
- 반복적인 코드를 줄이고, 도메인 특화 언어(DSL)를 구현하는 데 유용하지만, 남용하면 코드의 가독성을 해칠 수 있음

## 이터레이터 (Iterator)

- 컬렉션의 요소를 순회하기 위한 인터페이스를 제공하는 객체
- 컬렉션의 내부 구조를 노출하지 않고 요소에 접근할 수 있게 해주어, 코드의 유연성과 재사용성을 높일 수 있음

## 제네릭 프로그래밍 (Generic Programming)

- 타입을 매개변수화하여 재사용 가능한 코드를 작성하는 프로그래밍 패러다임
- 알고리즘이나 데이터 구조를 타입에 독립적으로 구현할 수 있게 해주어, 코드의 재사용성과 타입 안전성을 동시에 달성할 수 있음

## 타입 추론 (Type Inference)

- 컴파일러나 인터프리터가 표현식의 타입을 자동으로 유추하는 기능
- 코드의 가독성과 작성 편의성을 높일 수 있지만, 복잡한 타입 추론은 오히려 가독성을 해칠 수 있음

## null

- 객체 참조가 어떤 객체도 가리키지 않음을 나타내는 특수한 값
- 초기화되지 않은 변수나 유효하지 않은 참조를 표현하는 데 사용됨

## void

- 함수가 어떤 값도 반환하지 않음을 나타내는 특수한 타입
- 주로 부수 효과만을 위해 호출되는 함수의 반환 타입으로 사용됨

## 값 타입 (Value Type)

- 변수에 값 자체가 직접 저장되는 타입
- 할당 시 값이 복사되므로, 변수 간 값의 공유가 이루어지지 않음 (e.g., 정수, 실수, 불리언 등)

## 참조 타입 (Reference Type)

- 변수에 값이 저장된 메모리의 주소가 저장되는 타입
- 할당 시 참조가 복사되므로, 변수 간 동일한 객체를 공유할 수 있음 (e.g., 객체, 배열, 클래스 등)
