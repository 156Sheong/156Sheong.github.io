---
layout: single
title:  "정적과 인스턴스 개념 학습"
categories: TIL
tag: [Programming, TIL, CSharp]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 정적(Static)과 인스턴스(instance) 개념 학습
- 학습 목표
  - `static` 키워드의 정의와 사용법을 이해하고 설명할 수 있음
  - `static` 키워드 사용 시 주의점을 설명할 수 있음

- 주요 키워드
  -  **static**, **Data Area**


## A. 문서 이력
- 최초 작성일 : 2025-12-24
- 최종 수정일 : 2025-12-26

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 본과정 12일차 강의 내용,  등



## B. 정적과 인스턴스 란?
- **정적(Static)**과 **인스턴스(Instance)** 는 특정 기능과 속성이 결정되는 시점이 컴파일 시점인지, 런타임 시점인지에 따라 분류함
- **정적(Static)**
  - `static` 키워드가 붙은 메서드. 필드, 클래스 등
  - 객체를 생성할 필요 없이 `클래스_명.메서드_명`으로 바로 호출할 수 있음
  - 컴파일 시점이나 해당 클래스가 프로그램에서 처음 사용될 때 **데이터 메모리 영역(Data Area)**에 공간이 할당됨
  - 모든 인스턴스가 해당 메모리 공간을 공유, 값이 변경되면 모든 곳에서 변경됨
  - 프로그램 종료 시점까지 할당된 메모리가 유지 
  - 주로 **유틸리티 클래스(자주 사용하는 유용한 기능)**, **공유 데이터(누적 점수, 옵션 설정치)** 등을 구현할 때 사용
  - 예시 : `public static int Count = 0`, `Console.WriteLine()`

- **인스턴스(Instance)**
  - `static` 키워드 없이 선언하는 메서드, 필드, 클래스 등
  - `new` 키워드를 통해 객체를 생성한 뒤 `객체_명.메서드_명` 등으로 호출해야 함 
  - 변수가 선언되거나(스택 메모리), new 키워드를 통해 인스턴스를 생성할 때(힙 메모리) 메모리 영역의 한 공간이 할당됨
  - 객체(인스턴스) 마다 독립적으로 메모리 공간을 사용
  - 함수의 실행이 완료되거나(스택 메모리), 가비지 컬렉터가 더이상 참조되지 않는다고 판단할 때(힙 메모리) 메모리에서 제거됨
  - 객체마다 고유한 값이 필요할 때 사용, 객체지향 설계에서 필수적
  - 예시 : `public int InstanceCount = 0`


## C. 정적 필드 및 메서드 사용 예시
  ```csharp
  // 정적 필드와 인스턴스 필드를 선언할 클래스
  public class StaticStudy
  {
      public static int value1 = 10;  // 정적 필드
      public int value2 = 20; // 인스턴스 필드

      // 정적 메서드
      public static void Foo1()
      {
          Console.WriteLine("Call Foo1");
      }

      // 인스턴스 메서드
      public void Foo2()
      {
          Console.WriteLine("Call Foo2");
      }
  }

  // 클래스의 필드를 불러올 다른 클래스 및 함수
  internal class Tester
  {
      // 인스턴스 필드를 불러오기 위한 객체 생성
      private StaticStudy _study = new StaticStudy();

      public void Run()
      {
          Console.WriteLine(StaticStudy.value1);  // 10 출력, `클래스_명.필드_명` 의 구조로 불러옴
          Console.WriteLine(_study.value2); // 20 출력, `객체_명.필드_명` 의 구조로 불러옴

          StaticStudy.Foo1(); // Call Foo1 출력
          _study.Foo2();  // Call Foo1 출력
      }
  }
  ```

### Ca. (참고용) Console.WriteLine() 도 정적 메서드
- `System` 에 속한 `Console.WriteLine()` 도 `Console` 클래스에서 미리 정의된 정적 메서드
  ```csharp
  // ...
    [MethodImplAttribute(MethodImplOptions.NoInlining)]
    public static void WriteLine(object? value)
    {
        Out.WriteLine(value);
    }

    [MethodImplAttribute(MethodImplOptions.NoInlining)]
    public static void WriteLine(string? value)
    {
        Out.WriteLine(value);
    }

    [MethodImplAttribute(MethodImplOptions.NoInlining)]
    public static void WriteLine(ReadOnlySpan<char> value)
    {
        Out.WriteLine(value);
    }
  // ...
  ```


## D. 정적(Static) 사용 시 유의사항
### Da. 설계 측면의 유의사항
- 정적 키워드는 과도하게 사용 시 메모리에 부담을 줄 수 있음
- 정적 키워드는 데이터 메모리에 단 하나만 존재하기에, 복사하여 값을 변경해야하는 기능은 정적 키워드를 할당하면 안됨

### Db. 사용 측면의 유의사항
- 정적 클래스는 인스턴스를 생성할 수 없음 (`new` 키워드로 객체 생성 불가)
- 정적 키워드 내에선 인스턴스 멤버에 직접 접근할 수 없어서 다른 방법 필요 (반대로 인스턴스는 정적 멤버를 참조 가능)
  - 정적 메서드에서 인스턴스 멤버 활용 방법 예시
  ```csharp
  // 정적 메서드로 인스턴스 멤버 사용 방법 1
  public class ExmClass1
  {
      // int 형 인스턴스 변수
      public int InstNumber1 = 10;

      // 정적 메서드에서 매개변수로 인스턴스를 받아 출력
      public static void StaticFunc1(ExmClass1 class)
      {
          Console.WriteLine(class.InstNumber1); // int 형 인스턴스 변수
      }
  }

  // 메인 함수 내
  ExmClass1 instClass1 = new ExmClass1();
  ExmClass1.StaticFunc1(instClass1); // 출력: 10
  ```

  ```csharp
  // 정적 메서드로 인스턴스 멤버 사용 방법 2
  public class ExmClass2
  {
      public int InstNumber2 = 20;

      // 정적 메서드 내에서 새 인스턴스를 생성한 뒤 출력
      public static void StaticFunc2()
      {
          
          ExmClass2 instClass2 = new ExmClass2(); 
          Console.WriteLine(instClass2.InstNumber2); // int 형 인스턴스 변수
      }
  }

  // 메인 함수 내
  ExmClass2.StaticFunc2(); // 출력: 20 
  ```

- Static 생성자와 Public 생성자가 동시에 있을 때 유의사항
  - 해당 클래스에 접근하지 않는 경우, Static 생성자도 호출 안 됨
  - 여러 인스턴스를 생성해도, **Static 생성자는 1 번만 호출** 됨
  - **Static 생성자**는 `static` 키워드가 지정된 데이터만 제어 가능
  - **Static 클래스** 내부에는 `static` 키워드가 지정된 필드와 메서드만 가질 수 있음 (Static 클래스는 인스턴스를 만들지 못하기 때문)
  - 인스턴스 생성 시 **Static 생성자가 먼저 생성**되고, Public 생성자는 나중에 생성 됨
  - 인스턴스를 할당하지 않을 시(`new` 사용 X) 값, 함수에 접근하면 Static 생성자와 값, 함수만 호출 됨
    - 유의사항 관련 예시
    ```csharp
      // Public 생성자와 Static 생성자를 비교하기 위한 클래스
      public class StaticStudy2
      {
          public static int staticValue = 15;

          // 한 클래스는 public 생성자와 static 생성자를 각자 만들 수도 있음
          public StaticStudy2() { Console.WriteLine("Public 생성자"); }  // public 생성자
          static StaticStudy2() { Console.WriteLine("static 생성자"); }  // static 생성자
      }

      // 기능이 작동할 클래스 1
      internal class Tester2
      {
          private StaticStudy2 _class01;

          public void Run2()
          {
              _class01 = new StaticStudy2();  // static 생성자가 먼저 출력되고, public 생성자가 나중에 출력됨
          }
      }

      // 기능이 작동할 클래스 2
      internal class Tester3
      {
          private StaticStudy2 _class01;

          public void Run3()
          {
              Console.WriteLine(StaticStudy2.staticValue);    // new를 통한 객체 할당이 없이 클래스의 값이나 함수에 접근할 시, static 생성자와 staticValue 값만 출력됨
          }
      }
    ```
