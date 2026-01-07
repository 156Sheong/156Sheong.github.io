---
layout: single
title:  "스택과 큐 학습"
categories: TIL
tag: [Programming, TIL, CSharp, WIP]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 스택과 큐 학습
- 학습 목표
  - 선형 자료구조의 일종인 스택과 큐의 정의와 동작 방식을 이해하고 활용할 수 있음

- 주요 키워드
  - **선형 자료구조**, **스택**, **큐**, 



## A. 문서 이력
- 최초 작성일 : 2025-12-29
- 최종 수정일 : 2026-01-07

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 본과정 16일차 강의 내용 등



## B. 스택(Stack) 이란?
- **후입선출(LIFO: Last-In First-Out)** 구조의 자료형
- 데이터는 항상 **최상단** 에서만 **추가(Push)** 되거나 **제거(Pop)** 됨
- 스택은 내부적으로 배열로 구현되어있으나, 인덱서로 접근할 수 없음
- 게임에서 실행 취소할 때처럼 유저의 입력 등을 역순으로 타고 가야할 때 자주 사용됨



## B. 스택의 주요 메서드
- `.Push(number)`
  - 최상단에 데이터 추가
- `.Pop()`
  - 최상단의 데이터를 반환하고 스택에서 제거
- `.Peek()`
  - 최상단 데이터 확인 (추가나 제거 X)
- `.Contains(number)`
  - 스택에 특정 데이터가 있는지 확인
- `.Count`
  - 스택의 데이터 개수 확인
- `.Clear()`
  - 스택의 모든 데이터 제거



### Ba. 스택의 주요 메서드 사용 예시
```csharp
    static void Main(string[] args)
    {
        Stack<int> stack = new();

        // 스택 데이터 추가
        stack.Push(1);
        stack.Push(3);
        stack.Push(4);
        stack.Push(6);
        stack.Push(7);
        stack.Push(9);

        // 스택 데이터를 반환하고, 스택에서 제거함
        stack.Pop();    // int형의 9 제거
        stack.Pop();    // 7 제거
        stack.Pop();    // 6 제거

        // Stack의 가장 위에 있는 데이터를 확인
        Console.WriteLine(stack.Peek());    // 4 출력

        // Stack 에 특정 데이터가 있는지 확인
        Console.WriteLine(stack.Contains(3));    // true 출력

        // Stack에 남아있는 데이터를 반복문으로 출력
        foreach (int i in stack)
        {
            Console.WriteLine(i);    // 4, 3, 1 출력
        }

        // Stack에 남아있는 데이터를 모두 제거하는 반복문
        while (stack.Count > 0)
        {
            stack.Pop();
        }

        // Stack에 남아있는 데이터를 모두 제거하는 Clear() 메서드 사용해도 됨
        stack.Clear();

        // Stack이 비어있는지 확인
        if (stack.Count == 0)
        {
            Console.WriteLine("Stack이 비어있습니다.");
        }
    }
```



스택과 큐


내부적으로는 배열로 동일, 어떤 기능을 구현할지에 따라 후입선출, 선입선출인지 고려하여 정하는 것





큐 


Enquqe 삽입


스타 생산 예약, 턴제 게임에서 속도 순 캐릭터 순서 예약, 리플레이 데이터 등

머리와 꼬리에 해당하는 내부적인 배열  -head, _tail 함수 있음

TryDequque  큐(Queue)의 가장 앞쪽(처음)에 있는 요소를 안전하게 제거하고 반환하려는 메서드

