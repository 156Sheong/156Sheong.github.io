---
layout: single
title:  "확장 메서드 학습"
categories: TIL
tag: [Programming, TIL, CSharp]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 확장 메서드(Extension_Method) 학습
- 학습 목표
  - 확장 메서드에 대해 이해하고, 사용법을 숙지하며, 기존 메서드의 기능을 추가하여 사용할 수 있음

- 주요 키워드
  - **확장 메서드**


## A. 문서 이력
- 최초 작성일 : 2025-12-24
- 최종 수정일 : 2025-12-27

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 본과정 15일차 강의 내용, [MSDN 확장 멤버 문서](https://learn.microsoft.com/ko-kr/dotnet/csharp/programming-guide/classes-and-structs/extension-methods) 등



## B. 확장 메서드(Extension_Method) 란?
- 확장 메서드는 기존 클래스를 수정하지 않고도, 기존 형식(클래스, 구조체 등)에서 제공한 기능인 것 같은 메서드를 커스텀하여 새로 추가할 수 있게 해주는 기능
- 원본 코드 변경 불필요하고, 코드 재사용성이 향상되는 장점이 있음


## C. 확장 메서드 구현 방법
- 



    클래스 선언(정적) 하거나 인스턴스 안 만들고 사용할 수 있음






유니티에서는 Vector3 처럼 유니티 자체 정의 구조체나 기능 등이 있는데, 여기서 확장 메서드를 유용하게 사용할 수 있음

협업 시에 유용하게 사용 가능
    2d 탑뷰 시점 포물선 그리기 기능 등 (3D는 쉬움)


주의사항
    빈번하게 사용하지 않을 것 같은데 선언만 되어있으면 코드의 복잡성만 증가시키고, 협업 시에 헛갈리고, 시간만 많이 드니 주의


더 생각해보기
    확장 메서드는 OOP의  '개방 폐쇄 원칙' 을 지키기 위한 것일까요?
    -> 어거지로 엮을 수는 있지만 근본적으로는 다른 느낌