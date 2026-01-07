---
layout: single
title:  "스택과 큐 학습"
categories: TIL
tag: [Programming, TIL, CSharp]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 스택과 큐 학습
- 학습 목표
  - 선형 자료구조의 일종인 스택과 큐의 정의와 동작 방식을 이해하고 활용할 수 있음

- 주요 키워드
  - **스택**, **큐**



## A. 문서 이력
- 최초 작성일 : 2025-12-29
- 최종 수정일 : 2026-01-07

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 본과정 16일차 강의 내용 등



## B. 스택(Stack) 이란?
- **후입선출(LIFO: Last-In First-Out)** 구조의 **제네릭 컬렉션**
- 데이터는 **최상단** 에서만 **추가(Push)** 되거나 **제거(Pop)** 됨
- 스택은 내부적으로 배열로 구현되어있으나, 인덱서(`[i]`)로 접근할 수 없음
- 스택의 배열에 데이터가 다 차면 자동으로 배열의 크기를 2배로 확장하고 재할당함
  - 이 때, 기존의 배열은 가비지 컬렉션 대상이 됨
- 게임에서 실행 취소할 때처럼 유저의 입력 등을 역순으로 타고 가야할 때 자주 사용됨



## C. 스택의 주요 메서드
- `.Push(T item)`
  - 최상단에 데이터 추가
  - 시간 복잡도 : O(1)
- `.Pop()`
  - 최상단의 데이터를 반환하고 스택에서 제거
  - 시간 복잡도 : O(1)
- `.Peek()`
  - 최상단 데이터 확인 (추가나 제거 X)
  - 시간 복잡도 : O(1)
- `.Contains(T item)`
  - 스택에 특정 데이터가 있는지 확인
  - 시간 복잡도 : O(n)
- `.Count`
  - 스택의 데이터 개수 확인
  - 시간 복잡도 : O(1)
- `.Clear()`
  - 스택의 모든 데이터 제거
  - 시간 복잡도 : O(n)



### Ca. 스택의 주요 메서드 사용 예시
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



## D. 큐(Queue) 란?
- **선입선출(FIFO: First-In-First-Out)** 구조의 **제네릭 컬렉션**
- 데이터는 **꼬리(뒤)** 에서 **추가(Enqueue)** 되지만, **머리(앞)** 부터 **제거(Dequeue)** 됨
- 큐는 내부적으로 배열로 구현되어있으나, 인덱서(`[i]`)로 접근할 수 없음
- 큐는 내부적으로 머리(`_head`)와 꼬리(`_tail`)를 구분하는 필드가 있음
- 큐 배열에 데이터가 다 차면 자동으로 배열의 크기를 2배로 확장하고 재할당함
  - 이 때, 기존의 배열은 가비지 컬렉션 대상이 됨
- **너비 우선 탐색(BFS)**, **턴제 게임에서 속도 순으로 캐릭터 행동 예약**, **리플레이 데이터** 처럼 데이터를 들어온 순서대로 처리하는 상황에서 사용



## E. 큐의 주요 메서드
- `.Enqueue(T item)`
  - 꼬리에 데이터 추가
  - 시간 복잡도 : O(1)
- `.Dequeue()`
  - 머리의 데이터를 반환하고 큐에서 제거
  - 시간 복잡도 : O(1)
- `.TryDequeue(out T result)`
  - 큐의 머리의 데이터를 반환하고 큐에서 제거하고, 성공 여부를 bool 값으로 반환하는 메서드
  - 큐의 머리에 있는 요소를 안전하게 제거하고 반환하려고 할 때 사용
  - 시간 복잡도 : O(1)
- `.Peek()`
  - 머리의 데이터 확인 (추가나 제거 X)
  - 시간 복잡도 : O(1)
- `.Contains(T item)`
  - 큐에 특정 데이터가 있는지 확인
  - 시간 복잡도 : O(n)
- `.Count`
  - 큐의 데이터 개수 확인
  - 시간 복잡도 : O(1)
- `.Clear()`
  - 큐의 모든 데이터 제거
  - 시간 복잡도 : O(n)



### Ea. 큐의 주요 메서드 사용 예시
```csharp
    // 스타크래프트 속 테란 배럭의 유닛 생산 대기열 예시
    static public class Program
    {
        static void Main(string[] args)
        {
            Queue<Unit> barracks = new();

            // 배럭의 생산 대기열
            barracks.Enqueue(new Unit("Marine"));
            barracks.Enqueue(new Unit("Ghost"));
            barracks.Enqueue(new Unit("Firebat"));
            barracks.Enqueue(new Unit("Medic"));
            barracks.Enqueue(new Unit("Marine"));

            // 생산 시간 관련 함수

            // 먼저 입력받은 유닛부터 반환 후 대기열에서 제거
            Unit unit = barracks.Dequeue();

            // 남은 대기열 추가 순서부터 출력
            foreach(Unit u in barracks)
            {
                Console.WriteLine(u.Name);
            }
        }
    }

    public class Unit
    {
        public string Name { get; private set; }

        public Unit(string name)
        {
            Name = name;
        }
    }
```

머리와 꼬리에 해당하는 내부적인 배열  -head, _tail 함수 있음



