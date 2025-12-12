---
layout: single
title:  "디버거 기초 학습과 응용"
categories: Programming
tag: [Programming, TIL]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 디버거 기초 학습과 응용
- 학습 목표
  - 디버거의 활용법을 이해하고 실전에서 활용할 수 있는 것
  - 디버거에서 확인할 수 있는 컴퓨터의 이진수 표현법 이해와 실수형 자료 및 부동소수점에 대한 이해를 하는 것


## A. 문서 이력
- 최초 작성일 : 2025-12-11
- 최종 수정일 : 2025-12-12

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 본과정 4일차 강의 내용 등



## B. 디버거의 정의
- 디버거는 개발자가 임의의 프로그램 개발 중 프로그램을 테스트하고, 버그를 찾기 쉽도록 디버깅을 도와주는 개발자 도구
- Visual Studio 같은 통합 개발 환경(IDE)에는 **텍스트 에디터** - **빌더(컴파일러 포함)** - **디버거** 가 있음
- 디버거를 잘 활용하면 프로그램이 내부에서 연산되는 과정과, 각종 버그의 발생 원인을 좀 더 쉽게 찾을 수 있음

### Ba. 버그의 종류
- **문법 오류(Syntex Error)**
  - 프로그래밍 언어에서 사용되도록 고안된 키워드를 오기입하는 오류
  - 컴파일러가 어느 줄 어디에서 문제가 있는지 알려줌
- **논리적 오류(Logic Error)**
  - 컴파일이나 비정상적 종료는 아니지만, 의도치 않은 동작을 하는 오류
  - 컴퓨터는 인간의 의도를 모르기에, 개발자가 직접 찾아 고쳐야 함


## B. Visual Studio 디버거 기초 기능



## C. Visual Studio 디버거 응용

커스텀 조사식

Convert.ToString(변수, '진법') -> 이거 콘솔창에 해서 디버깅에서 활용할 수도 있음

일부러 디버깅용 함수를 만들고 거기 중단점을 설정한 뒤 디버깅해서 편의성을 챙길 수도 있음

Visual Studio 디버거에서 &(주소 연산자)는 변수의 메모리 주소를 확인할 때 사용


  Visual Studio 디버거 기능 심화
오버플로우 막는 방법
더 큰 데이터 형식을 사용해서 미리 계산해보고 잘되면 실제 식을 수행
long 형으로 미리 계산해보고 잘 되는지 보고 int 형으로 가기



## D. Visual Studio 로 정수와 실수 살펴보기







  콘솔 실행 중지시키고 싶을 때
콘솔 창 닫기
Ctrl + C
 - 현재까지의 출력 상황 확인 가능, 이어서 진행은 줄가



F5 : 디버거에 연결해 중단점까지 실행
Ctrl + F5 : 디버거에 연결하지 않고 콘솔로 프로그램 실행
F9 : 중단점, 비주얼 스튜디오 화면 좌측 에서 눌러도 됨, 여러 중단점 설정 가능
F10 : 프로시저 단위(Visual Studio 에서 한 줄) 실행
F11 : 한 단계씩 코드 실행











이진법
십육진법
비트 시프트
2의 보수법
8 비트 = 1 바이트
WORD = 16 비트, 과거 CPU가 메모리에서 데이터를 가져올 때 한번에 16비트를 가져와서 데이터를 처리하던 시절 단위, 현재는 64비트 가져와서 처리함
DWORD = Double WORD = 32 비트
QWORD = Quad WORD = 64 비트

디버거로 보면 실수가 부정확하게 나오는 것을 볼 수 있음



https://learn.microsoft.com/ko-kr/visualstudio/debugger/debugging-absolute-beginners?view=visualstudio&tabs=csharp

https://learn.microsoft.com/ko-kr/visualstudio/debugger/debugger-feature-tour?view=visualstudio

https://learn.microsoft.com/ko-kr/dotnet/csharp/language-reference/language-specification/expressions#1247-numeric-promotions

https://blog.naver.com/songsite123/223053243600

https://zapiro.tistory.com/entry/Visual-Studio-%EB%94%94%EB%B2%84%EA%B1%B0-%EC%82%AC%EC%9A%A9%EB%B2%95
