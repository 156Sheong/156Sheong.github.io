---
layout: single
title:  "인터페이스 학습"
categories: TIL
tag: [Programming, TIL, CSharp]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 인터페이스(Interface) 학습
- 학습 목표
  - 인터페이스의 목적을 알고 사용법을 활용할 수 있음

- 주요 키워드
  - **인터페이스**


## A. 문서 이력
- 최초 작성일 : 2025-12-24
- 최종 수정일 : 2025-12-29

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 본과정 13일차 강의 내용,  등



## B. 인터페이스 란?

인터페이스는 클래스처럼 보이지만 구현이 없다. 여기에는 이벤트, 인덱서, 메서드 또는 속성의 선언만 포함
인터페이스가 선언만 제공하는 이유는 선언된 각 인터페이스 멤버에 대한 구현을 제공해야 하는 구조체 및 클래스에 의해 상속되기 때문
인터페이스는 여러 가지 이유로 유용하다. 더 큰 추상화를 허용하여 유연하고 재사용 가능한 코드를 더 쉽게 작성 가능
서로 다른 형식의 객체가 동일한 인터페이스를 구현하는 한 서로 상호 작용 가능 이것이 바로 다형성


추상 클래스는 구현을 포함할 수 있지만 인터페이스는 포함할 수 없다.
인터페이스는 오직 다른 인터페이스를 상속할 수 있다. 그러나 추상 클래스는 다른 클래스와 인터페이스 다 상속받을 수 있다.
한 클래스가 여러 인터페이스 동시에 상속 가능
추상 클래스는 생성자 소멸자를 포함한다. 하지만 인터페이스는 포함하지 않는다.
추상 클래스는 필드를 가진다. 하지만 인터페이스는 가지지 않는다.


// 인터페이스 정의 (청사진)
public interface IShape // I로 시작
{
    void Draw(); // 구현이 없는 메서드 시그니처
    double GetArea(); // 구현이 없는 메서드 시그니처
}

// 인터페이스 구현 (청사진을 이용한 실제 설계도)
public class Circle : IShape // IShape 인터페이스 구현
{
    public double Radius { get; set; }

    public void Draw() // Draw 메서드 구현
    {
        Console.WriteLine("원을 그립니다.");
    }

    public double GetArea() // GetArea 메서드 구현
    {
        return Math.PI * Radius * Radius;
    }
}


public interface ICanFly {
    void Fly();
}

public interface ISpeak {
    void Speak();
}

public class Bird : ICanFly, ISpeak
{
    public void Fly()
    {
        Console.WriteLine("나는 날 수 있다.");
    }

    public void Speak()
    {
        Console.WriteLine("나는 소리 낼 수 있다.");
    }
}