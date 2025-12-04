---
layout: single
title:  "변수 및 자료형 학습(초반에 만든 포스트라 추가 정리 필요)"
categories: Programming
tag: [Programming, TIL, CSharp]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 변수(Variable)와 자료형(Data Type) 학습
- 학습 목표 : C#에서 활용 가능한 주요 변수와 자료형을 이해하는 것



## A. 문서 이력
- 최초 작성일 : 2025-11-20
- 최종 수정일 : 2025-12-05

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 온보딩 캠프 3일차 강의 내용, [마이크로소프트 C# 기본 제공 형식 문서](https://learn.microsoft.com/ko-kr/dotnet/csharp/language-reference/builtin-types/built-in-types) 등



## B. 변수와 상수 설명
- 변수와 상수는 값을 저장하기 위한 이름이 있는 메모리 공간
- 변수와 상수는 특정 자료형(Data Type) 가짐
  
- **변수(Variable)**
  - 프로그램이 실행되는 동안 값이 변경될 수 있는 메모리 공간
  - 변수 안에 저장된 값은 언제든지 변경될 수 있음
  
- **상수(constant)**
  - 한 번 할당되면 프로그램 실행 중 절대 변경할 수 없는 값(변경하려고 시도하면 오류 발생)
  - 변수 선언 시, 변수명 앞에 const 를 붙임
  - 예시 : const int maxHP = 100;



## B. 자료형의 종류와 설명
- 정수형
  - int
  - uint
  - long
  - ulong
- 실수형
  - float
  - double
  - decimal
- 문자형
  - char
  - string
- 논리형
  - bool
- 시퀀스형
  - list
  - tuple
- 매핑형
  - dictionary

- 변수명 규칙
  - 파스칼 케이스
  - 카멜 케이스

- 변수 선언과 값 대입 주요 규칙
  - 컴퓨터는 코드를 메인이라는 시작점의 중괄호부터 읽기 시작
  - 변수를 저장할 목적의 공간 확보 코드(변수 선언)가 나오면 요청된 공간만큼 자리 확보
  - 특정 수를 변수에 대입하라는 코드를 만나면 식별자를 보고 그 공간으로 가서 값 대입
  - 변수 선언과 동시에 값을 대입(변수 초기화) 가능

- 상수형(constant)
  - 변수 선언 시, 변수명 앞에 const 를 붙임
  - 예시 : const int maxHP = 100;