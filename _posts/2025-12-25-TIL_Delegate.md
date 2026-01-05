---
layout: single
title:  "델리게이트와 이벤트 학습"
categories: TIL
tag: [Programming, TIL, CSharp, WIP]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 델리게이트(Delegate)와 이벤트 학습
- 학습 목표
  - 델리게이트와 이벤트를 이해하고 사용할 수 있음
  - 람다식을 사용해 코드를 간결하게 작성할 수 있음

- 주요 키워드
  -  **델리게이트**, **이벤트**, **람다식**


## A. 문서 이력
- 최초 작성일 : 2025-12-24
- 최종 수정일 : 2025-12-25

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 본과정 13일차 강의 내용,  등



## B. 델리게이트 란?
- 메서드를 안전하게 참조할 수 있는 '함수 포인터' 같은 개념
- 특정 메서드의 주소를 저장했다 나중에 필요할 때 호출할 수 있는 형식




// 델리게이트 선언: int를 받고 int를 반환하는 메서드를 참조
public delegate int MyDelegate(int a, int b);

// 델리게이트에 할당될 메서드들
public int Add(int x, int y) { return x + y; }
public int Subtract(int x, int y) { return x - y; }

// 델리게이트 변수 생성 및 메서드 할당
MyDelegate operation = new MyDelegate(Add);
// C# 2.0 이후 축약 형태: MyDelegate operation = Add;

// 델리게이트를 통해 메서드 호출
int result = operation(5, 3); // Add(5, 3) 호출, 결과는 8