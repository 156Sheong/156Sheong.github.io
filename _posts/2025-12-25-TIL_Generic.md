---
layout: single
title:  "제네릭 학습"
categories: TIL
tag: [Programming, TIL, CSharp, WIP]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 제네릭(Generic) 학습
- 학습 목표
  - 박싱과 언박싱의 개념에 대해 이해할 수 있음
  - 제네릭의 개념과 필요성, 사용 방법을 숙지할 수 있음

- 주요 키워드
  - **박싱**, **언박싱**, **제네릭**


## A. 문서 이력
- 최초 작성일 : 2025-12-24
- 최종 수정일 : 2025-12-25

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 본과정 13일차 강의 내용,  등



## B. 제네릭 이란?

클래스, 인터페이스, 메서드 등에서 사용할 데이터 타입을 정의 시점이 아닌 사용 시점에 결정하도록 만드는 기능



public class Box<T>
{
    public T Content { get; set; }
}

// 사용 예시
Box<int> intBox = new Box<int> { Content = 100 };
Box<string> strBox = new Box<string> { Content = "Hello" };


public void Swap<T>(ref T a, ref T b)
{
    T temp = a;
    a = b;
    b = temp;
}





public void Swap<T>(ref T a, ref T b) : where T : struct
{
    T temp = a;
    a = b;
    b = temp;
}



제약 조건 	설명
where T : struct	T는 반드시 값 타입이어야 함
where T : class	T는 반드시 참조 타입이어야 함
where T : new()	T는 매개변수가 없는 공용 생성자가 있어야 함
where T : BaseClass	T는 지정된 기본 클래스 또는 그 파생 클래스여야 함
where T : InterfaceName	T는 지정된 인터페이스를 구현해야 함



System.Collections.Generic 네임스페이스에 있는 클래스들이 가장 많이 사용됩니다. 
List<T>: 가변 크기 배열
Dictionary<TKey, TValue>: 키-값 쌍의 컬렉션
Queue<T>, Stack<T> 등 