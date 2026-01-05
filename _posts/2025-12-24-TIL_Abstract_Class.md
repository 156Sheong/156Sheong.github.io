---
layout: single
title:  "추상 클래스 학습"
categories: TIL
tag: [Programming, TIL, CSharp, Patch]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 추상 클래스(Abstract Class) 학습
- 학습 목표
  - 추상 클래스와 다형성을 이해하고 사용할 수 있음

- 주요 키워드
  -  **추상 클래스**, **다형성**, `abstract`, `protected`



## A. 문서 이력
- 최초 작성일 : 2025-12-24
- 최종 수정일 : 2025-12-25

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 본과정 12일차 강의 내용,  등



## B. 추상 클래스 란?
- 객체를 생성할 수 없고(`new` 키워드 사용 불가), 다른 클래스의 부모 역할만 할 수 있는 미완성 클래스
  - 추상 클래스만 부모 클래스가 될 수 있는 것은 아닌 것을 주의
- 추상 클래스는 다른 클래스에 상속을 준 후, 추가 기능을 하위 클래스에서 구현하도록 강제함 (하지 않으면 에러가 뜸)
- 다른 클래스가 상속 받아 구현해야 하는 공통 기능이나 일반 멤버를 정의하는데 사용됨
- 멤버 이름을 맞추고 싶을 시, 추상 클래스에서 먼저 정의하고 자식 클래스에서 해당 멤버를 구현함(override 사용)
- 추상 클래스는 `public` 같은 액세스 한정자를 가짐
- 추상 클래스는 멤버로 속성, 생성자, 소멸자, 메서드, 이벤트, 인덱서를 가짐
- 자식 클래스는 하나의 추상 클래스만 상속받을 수 있음



## C. 추상 클래스 사용법
- 추상 클래스는 `abstract` 키위드를 사용하여 선언
- 자식 클래스에서 부모 클래스인 추상 클래스를 재정의 해야함
- 추상 클래스에서 `abstract` 키위드를 붙인 추상 메서드도 제작 가능하고, 이 경우에는 자식 클래스에서 메서드를 재정의 해야
- 추상 클래스에서 `protected` 키워드를 붙인 필드를 선언하면 자식 클래스에서만 필드 제어 가능함
- 추상 클래스 사용법 예시
    ```csharp
    public abstract class Factions  // 부모가 되는 추상 클래스
    {
        public abstract int factionID { get; set; } // 추상 메서드의 경우 자식 클래스의 메서드에서 구현해야 함
        public string factionName { get; set; }
    }

    public class SteppeConfederacy : Factions // 자식이 되는 클래스
    {
        public override int factionID { get; set; } // 추상 메서드는 자식 클래스 내에서 재정의 해야함
    }

    // 추상 클래스를 사용하는 Main 함수
    public class Program
    {
        static void Main(string[] args)
        {
             // 추상 클래스는 인스턴스를 만들 수 없기 때문에, `new` 할당 시 자식 클래스로 인스턴스를 선언해야 함
            SteppeConfederacy runProgram01 = new SteppeConfederacy();
            Factions runProgram02 = new SteppeConfederacy();  // 부모 클래스를 변수 타입으로 하고, 인스턴스를 자식 클래스로 선언할 수도 있음
        }
    }
    ```