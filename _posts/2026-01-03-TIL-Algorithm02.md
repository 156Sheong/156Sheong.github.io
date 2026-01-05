---
layout: single
title:  "알고리즘의 복잡도와 Big-O 학습"
categories: TIL
tag: [Programming, TIL, CSharp]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---


# 알고리즘의 복잡도와 Big-O 학습
- 학습 목표
  - 

- 주요 키워드
  - **공간 복잡도**, **시간 복잡도**, **Big-O**


## A. 문서 이력
- 최초 작성일 : 2026-01-03
- 최종 수정일 : 2026-01-05

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 본과정 20일차 강의 내용, [빅오(Big-O)표기법 쉽게 이해하기](https://youtu.be/5Ky59iblLBI?si=qLdmPEM2OY07CINx) 영상 등


## B. 알고리즘의 복잡도 란?
- 알고리즘의 복잡도는 알고리즘이 실행될 때 필요한 컴퓨팅 자원(시간과 메모리)의 양을 나타내는 척도
- 알고리즘의 복잡도에는 **시간 복잡도**, **공간 복잡도** 가 있음
- 복잡도가 낮을수록 더 효율적인 알고리즘
- **시간 복잡도(Time Complexity)**
  - 알고리즘이 문제를 해결하는 데 걸리는 시간의 양
  - 연산 횟수를 기준으로 측정하고, 입력 데이터의 크기(n)이 커짐에 따라 실행 시간이 얼마나 빠르게 증가하는지를 파악
- **공간 복잡도(Space Complexity)**
  - 알고리즘을 실행하는 데 필요한 총 메모리 공간의 양
  - 입력 크기에 따른 필요한 메모리 양의 증가율을 분석함


## C. 알고리즘의 복잡도를 표시하는 방법
- **Big-O 표기법**
  - 점근적 표현법 중 하나로, 알고리즘 최악의 실행 시간을 표기
  - 연산 횟수 계산법을 하나의 일관된 형식으로 만들어주어, 알고리즘의 런타임이 인풋 증가량에 따라 얼마나 증가하는지를 설명할 수 있게 해줌
  - 최소한 보장되는 성능을 표기하기 때문에 가장 일반적으로 사용됨
- **Big-Ω 표기법**
  - 법 알고리즘 최상의 실행 시간을 표기
- **Big-θ 표기법**
  - 알고리즘 평균 실행 시간을 표기


## D. Big-O 표기법의 규칙
- 최고차항만 표기 & 상수항과 영향력 없는 항은 무시
  - T(f) = n * (3n + 200) + 100 일 경우, T(f) = 3n^2만 표기
- 계수를 무시
  - T(f) = 3n^2일 경우, T(f) = n^2 으로 표기
  - 따라서 T(f) = O(n^2)


## D. Big-O의 활용과 주요 시간 복잡도
- Big-O 표기법의 주요 시간 복잡도는 **O(1)**, **O(logn)**, **O(n)**, **O(n^2)**, **O(n!)** 등이 있음
- **O(1)** > **O(logn)** > **O(n)** > **O(n^2)** > **O(n!)** 순으로 처리 속도가 좋고 효율적임
- **O(1)**
  - 인풋의 크기와 상관없이 항상 일정한 시간 소요
  - `stack`의 `push`, `pop` 등 이 대표적
  - 예시 소스 코드
    ```csharp
      public void GetFirstElement(int[] arr)
      {
        return arr[0];  // 인풋 크기에 상관 없이 가장 앞의 인덱스를 지닌 배열을 뱉어냄
      }
    ```
- **O(logn)**
  - 인풋의 크기의 로그에 비례한 시간 소요
  - binary search 알고리즘, tree 형태 자료구조 탐색 등이 대표적
  - 예시 소스 코드
    ```csharp
      public void GetLogCounter(int n)
      {
        int loopCount = 0;
        for(int i = 2; i < n; i *= 2)
        {
          loopCount++;
        }
        return loopCount; // 인풋이 2면 for 문 1회 수행, 16이면 4회 수행
      }
    ```
- **O(n)**
  - 인풋의 크기에 정비례한 시간 소요
  - 1중 for문 등
- **O(n^2)**
  - 인풋의 크기의 제곱에 비례한 시간 소요
  - 2중 For 문, 삽입 정렬, 거품 정렬, 선택 정렬 등
- **O(2^n)**
  - 인풋의 크기의 2^n 승에 비례한 시간 소요
  - 피보나치 수열의 재귀 구현 등
  - 예시 소스 코드
    ```csharp
      public int Fibonacci(int n)
      {
          // 자기 자신을 두 번씩 호출
          if (n <= 1) return n;
          return Fibonacci(n - 1) + Fibonacci(n - 2);
      }
    ```
- **O(n!)**
  - 인풋의 크기의 팩토리얼 승에 비례한 시간 소요
  - 문자열의 모든 순열 생성, 외판원 순회 문제(TSP)의 브루트 포스 탐색 등
    ```csharp
      public void Permute(string str, string result)
      {
          if (str.Length == 0)
          {
              Console.WriteLine(result);
              return;
          }

          for (int i = 0; i < str.Length; i++)
          {
              char ch = str[i]; // 현재 순서에 올 문자 하나를 선택
              string rest = str.Substring(0, i) + str.Substring(i + 1); // 선택한 문자를 제외한 나머지 문자열 생성
              Permute(rest, result + ch); // 남은 문자들로 다음 자리를 채우기 위해 재귀 호출
          }
      }
    ```