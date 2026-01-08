---
layout: single
title:  "오브젝트와 제네릭 학습"
categories: TIL
tag: [Programming, TIL, CSharp]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 오브젝트와 제네릭 학습
- 학습 목표
  - 박싱과 언박싱의 개념에 대해 이해할 수 있음
  - 제네릭의 개념과 필요성을 이해하고, 사용 방법을 숙지할 수 있음

- 주요 키워드
  - **박싱**, **언박싱**, **제네릭**, **object**


## A. 문서 이력
- 최초 작성일 : 2025-12-24
- 최종 수정일 : 2025-01-09

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 본과정 13일차 강의 내용, [MSDN Object 클래스 문서](https://learn.microsoft.com/ko-kr/dotnet/api/system.object?view=net-8.0), [MSDN 제네릭 클래스 및 메서드 문서](https://learn.microsoft.com/ko-kr/dotnet/csharp/fundamentals/types/generics) 등



## B. 오브젝트(Objcet) 란?
- 오브젝트는 C#의 모든 클래스, 구조체, 기본 타입 등이 상속받는 최상위 타입
- 어떤 타입의 데이터든 `object` 타입 변수에 할당 가능하고, **실제 타입은 런타임에 결정**됨
- 값 타입(`struct`, `int`, `bool` 등)이 참조 타입인 `object` 로 변환될 때 **박싱(Boxing)** 을 하며 힙 메모리에 할당됨
- **박싱** 된 타입이 다시 원래 타입으로 변환될 때 **언박싱(Unboxing)** 을 함
- **박싱** 과 **언박싱** 과정에서 성능 저하를 유발함
- `var` 키워드도 명시적인 타입 선언 없이 변수 선언할 수 있어 유사해보이나, 근본적인 동작은 다름
  - `var`는 컴파일 시점에 타입이 결정되는 정적 타입
  - `object`는 런타임에 타입이 결정되는 최상위 클래스 타입


### Ba. C# 타입 간의 관계 이미지
  ![alt text](/images/2025-12-25-TIL_Generic/TIL_Generic_Img000.png)



## C. 오브젝트 박싱 / 언박싱 사용법 및 예시
- 박싱은 암시적으로 발생
- 언박싱은 명시적으로 선언해야 함


### Ca. 오브젝트 사용 시 고려 사항
- 오브젝트 형식은 직접 쓸 일은 많이 없음
- 그러나 유니티 내에서 자체적으로 사용하는 경우가 있음
  - 대표적으로 게임 저장 등 json 유틸리티 에서 사용
- 언박싱에서 문제가 생길 수 있으니, 문제점 명확히 인지하는 것이 중요
  - 잘못된 타입으로 캐스팅할 경우 런타임 에러 발생
  - 성능 저하 등


### Cb. 오브젝트 사용 예시
  ```csharp
    int a = 5;

    // a의 데이터를 복사해 힙 메모리에 할당. 박싱
    // 암시적으로 발생
    object b = a;

    // b의 데이터를 복사해 스택 메모리에 할당. 언박싱
    // 명시적으로 선언해야 함
    int c = (int)b;
  ```



## D. 제네릭(Generic) 이란?
- `object` 타입과는 다르게, 박싱 / 언박싱 단계를 거치지 않고 여러 데이터 타입을 안전하게 다룰 수 있음
- 사용할 데이터 타입을 **컴파일 단계에서 올바른 형식을 적용**해 타입 안정성이 보장
- `object` 을 대체할 수 있는 C#의 기능
- `object` 타입 보다 간결하고, 직관적인 코드 작성이 가능함


## E. 제네릭 사용법 및 예시
- 함수에 사용 시, `함수명<T>(ref T a, ref T b)` 와 같은 형태로 사용
  - T는 어떤 타입도 들어올 수 있음 (값타입, 참조타입 둘 다 가능)
- 함수 제네릭 선언, 클래스 제네릭 둘 다 가능


### Ea. 제네릭 제약 조건
- 제네릭에는 특정 타입의 자로형만 가능하도록 제약 조건을 걸어줄 수 있음
- 제약 조건 예시
  - `where T : struct`
    - T는 반드시 값 타입이어야 함
  - `where T : class`
    - T는 반드시 참조 타입이어야 함
  - `where T : new()`
    - T는 매개변수가 없는 공용 생성자가 있어야 함
      - 인자를 받아서 생성 불가능
  - `where T : BaseClass`
    - T는 지정된 기본 클래스 또는 그 파생 클래스여야 함
  - `where T : InterfaceName`
    - T는 지정된 인터페이스를 구현해야 함


### Eb. 제네릭 사용 예시
- 제네릭은 유니티에서 자주 사용해볼 수 있음
- C# 에선 의식하지 않아도 제네릭을 자주 사용하게 됨
- `System.Collections.Generic` 네임스페이스에 있는 대부분의 클래스에서 **제네릭** 을 사용해서 구현함
  - List<T>, Dictionary<TKey, TValue>, Queue<T>, Stack<T> 등 

- 일반적인 사용 예시
  ```csharp
    // 값 타입 / 참조 타입에 상관 없이, 두 자료형(두 자료형이 동일해야 함)의 위치를 서로 바꿔주는 함수
    // T 라는 문자는 제네릭을 만들 때 암묵적으로 사용하는 기호
    public void Swap<T>(ref T a, ref T b)
    {
      T temp = a;
      a = b;
      b = temp;
    }
  ```

- 값 타입 / 참조 타입만 사용할 수 있는 경우 사용 예시
  ```csharp
  // 값 타입 자료형의 위치를 서로 바꿔주는 함수
    public void Swap<T>(ref T a, ref T b) : where T : struct
    {
        T temp = a;
        a = b;
        b = temp;
    }

    // 참조 타입 자료형의 위치를 서로 바꿔주는 함수
    public void Swap<T>(ref T a, ref T b) : where T : class
    {
        T temp = a;
        a = b;
        b = temp;
    }
  ```

- 반환형 사용 예시
  ```csharp
    public void GetValue<T>(ref T a)
    {
      return a;
    }
  ```

- 클래스에 사용 예시
  ```csharp
    // 클래스에 제네릭 사용
    public class Box<T>
    {
        private T[] _arr = new T[10];

        public void Add(T value)
        {

        }

        public T Get(int index)
        {
          return _arr[index];
        }

        public T Content { get; set; }
    }

    // 사용 부분
    Box<int> intBox = new Box<int> { Content = 100 };
    Box<string> strBox = new Box<string> { Content = "Hello" };
  ```

- 특정 클래스를 상속 받아야하는 사용 예시
  ```csharp
    // 상속할 부모 클래스에 제네릭 사용
    public class Container<T> where T : Character
    {

    }
    
    // : Character 부분이 없으면 Monster 클래스는 Container<T> 클래스를 상속받을 수 없음
    public class Monster : Character
    {

    }
    
    // 상속받은 클래스의 인스턴스 생성부
    Public void Run()
    {
      Container<Monster> _monsterContainer = new Container<Monster>();  // T = Monster
    }
  ```






