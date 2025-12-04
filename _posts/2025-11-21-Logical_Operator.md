---
layout: single
title:  "논리 연산자와 조건문 학습"
categories: Programming
tag: [Programming, TIL, CSharp]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 논리 연산자(Logical Operator)와 조건문(Conditional Statement) 연습
- 학습 목표 : C#에서 활용 가능한 논리 연산자와 조건문 학습



## A. 문서 이력
- 최초 작성일 : 2025-11-21
- 최종 수정일 : 2025-11-21

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 온보딩 캠프 5일차 강의 내용, [명지대학교 이산수학 유튜브](https://youtu.be/2XLwJDi_Q4Y?si=iTACz1gX2aCNLdeY) 등



## B. 논리 연산자에 대하여
- 둘 이상의 조건식 또는 불 값을 결합해 단일의 참 / 거짓 결과를 반환하는데 사용되는 연산자
- 논리 연산자의 종류
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-nfnx{background-color:#1f5059;border-color:inherit;font-weight:bold;text-align:center;vertical-align:middle}
.tg .tg-rcip{background-color:#2f414a;border-color:inherit;text-align:center;vertical-align:middle}
</style>
<table class="tg"><thead>
  <tr>
    <th class="tg-nfnx">종류</th>
    <th class="tg-nfnx">기호</th>
    <th class="tg-nfnx">설명</th>
    <th class="tg-nfnx">단축 평가 여부</th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-rcip">조건부 AND</td>
    <td class="tg-rcip">&amp;&amp;</td>
    <td class="tg-rcip">두&nbsp;&nbsp;&nbsp;개의 피연산자가 모두 TRUE일 때만 TRUE로 반환,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;한 쪽이라도 FALSE면 FALSE로 반환</td>
    <td class="tg-rcip">왼쪽&nbsp;&nbsp;&nbsp;피연산자 먼저 평가 -&gt; 값이 FALSE 이면 우측 피연산자는 평가 건너뜀</td>
  </tr>
  <tr>
    <td class="tg-rcip">비조건부 AND</td>
    <td class="tg-rcip">&amp;</td>
    <td class="tg-rcip">두&nbsp;&nbsp;&nbsp;개의 피연산자가 모두 TRUE일 때만 TRUE로 반환,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;한 쪽이라도 FALSE면 FALSE로 반환</td>
    <td class="tg-rcip">X</td>
  </tr>
  <tr>
    <td class="tg-rcip">조건부 OR</td>
    <td class="tg-rcip">||</td>
    <td class="tg-rcip">두&nbsp;&nbsp;&nbsp;개의 피연산자 중 하나가 TRUE면 TRUE로 반환,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;두 피연산자 모두 FALSE면 FALSE로 반환</td>
    <td class="tg-rcip">왼쪽&nbsp;&nbsp;&nbsp;피연산자 먼저 평가 -&gt; 값이 TRUE 이면 우측 피연산자는 평가 건너뜀</td>
  </tr>
  <tr>
    <td class="tg-rcip">비조건부 OR</td>
    <td class="tg-rcip">|</td>
    <td class="tg-rcip">두&nbsp;&nbsp;&nbsp;개의 피연산자 중 하나가 TRUE면 TRUE로 반환,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;두 피연산자 모두 FALSE면 FALSE로 반환</td>
    <td class="tg-rcip">X</td>
  </tr>
  <tr>
    <td class="tg-rcip">배타적 논리합 XOR</td>
    <td class="tg-rcip">^</td>
    <td class="tg-rcip">두&nbsp;&nbsp;&nbsp;개의 피연산자의 값이 서로 다를 경우에만 TRUE로 반환,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;두피연산자의 값이 서로 같을 경우 FALSE로 반환</td>
    <td class="tg-rcip">X</td>
  </tr>
  <tr>
    <td class="tg-rcip">논리 부정 NOT</td>
    <td class="tg-rcip">!</td>
    <td class="tg-rcip">단항&nbsp;&nbsp;&nbsp;연산자로, 피연산자의 논리 값을 반대로 뒤집음,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;!TRUE -&gt; FALSE / !FALSE -&gt; TRUE</td>
    <td class="tg-rcip">X</td>
  </tr>
</tbody></table>



## C. 조건문에 대하여
- 프로그램 실행 중에 특정 조건식의 평가 결과(TRUE / FALSE)에 따라 다르게 동작하는, 코드의 실행 흐름을 제어하는 데 사용하는 구문
- 주어진 조건식이 참(TURE)이면 특정 코드 블록을 실행하고, 거짓(FALSE)이면 다른 코드 블록을 실행하거나 건너뛰는 형태로 작동



## D. 주요 조건문의 형태
- if / else if / else 문
  - 사용 예시
  
  ```csharp
  public enum StamState
  {
      Fresh,       
      Normal,      
      Tired,       
      Exhausted    
  }

  public StamState StaminaCondition(float currentStam,float maxStam)
  {
    StamState currentState;

    if(currentStam / maxStam > 0.75)
    {
      currentState = StamState.Fresh;
    }
    else if(currentStam / maxStam > 0.5)
    {
      currentState = StamState.Normal;
    }
    else if(currentStam / maxStam > 0.25)
    {
      currentState = StamState.Tired;
    }
    else
    {
      currentState = StamState.Exhausted;
    }

    return currentState;
  }
  ```

- switch / case 문
  - 사용 예시
  
  ```csharp
  public enum GameDifficulty
  {
      Casual = 0, // 캐주얼
      Standard = 1, // 표준
      Advanced = 2, // 숙련자
      Challenging = 3,  // 도전
      Insane = 4  // 광기
  }

  public void PrintGameDifficulty(GameDifficulty selectDifficulty)
  {
    GameDifficulty currentDifficulty;
    
    switch(selectDifficulty)
    {
      case GameDifficulty.Standard:
        currentDifficulty = selectDifficulty;
        Console.WriteLine("표준 난이도 입니다");
        break;
      case GameDifficulty.Advanced:
        currentDifficulty = selectDifficulty;
        Console.WriteLine("숙련자 난이도 입니다");
        break;
      case GameDifficulty.Challenging:
        currentDifficulty = selectDifficulty;
        Console.WriteLine("도전 난이도 입니다");
        break;
      case GameDifficulty.Insane:
        currentDifficulty = selectDifficulty;
        Console.WriteLine("광기 난이도 입니다");
        break;
      default:
        currentDifficulty = selectDifficulty;
        Console.WriteLine("캐주얼 난이도 입니다");
        break;
    }
  }
  ```