---
layout: single
title:  "디버깅 및 유니티 프로파일러 기초 학습"
categories: Programming
tag: [Programming, TIL, CSharp]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 디버깅(Debugging) 및 유니티 프로파일러(Profiler) 기초 학습
- 학습 목표 : C#에서 활용 가능한 디버깅 및 프로파일러 학습



## A. 문서 이력
- 최초 작성일 : 2025-11-27
- 최종 수정일 : 2025-11-27

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 온보딩 캠프 9일차 강의 내용, [마이크로소프트 Learn 디버거 설명](https://learn.microsoft.com/ko-kr/visualstudio/debugger/debugger-feature-tour?view=visualstudio) 등



## B. 디버깅의 정의
- 코드가 예상대로 작동하지 않을 때, 코드 내 버그를 식별하고, 위치를 찾아내며, 수정하는 과정
- 비주얼 스튜디오의 경우 통합 디버거를 활용해 버그를 빠르게 찾아낼 수 있음



## C. 디버깅 과정 및 방법
1. 문제 재현 : 버그가 발생한 특정 시나리오나 입력값을 찾음
2. 격리 및 분석
   - 비주얼 스튜디오 디버거 등을 사용하여 프로그램 실행을 중단, 버그가 발생한 코드 영역을 격리함
   - 변수 값, 호출 스택, 메모리 상태 등 검사해 원인을 분석
3. 가설 수립 및 수정 : 문제의 근본 원인에 대한 가설을 세우고 코드를 수정해 문제를 해결
4. 검증 및 회귀 테스트
    - 수정된 코드를 실행해 버그가 해결되었는지 확인
    - 새로운 버그가 발생하지 않도록 관련 테스트 수행



## D. 비주얼 스튜디오의 주요 디버깅 도구 및 기술
- 중단점(Breakpoints) : 코드의 특정 줄에서 프로그램 실행을 일시 중지함
- 조사식(Watch) 창 / 자동(Autos) 창 / 지역(Locals) 창 : 중단점에서 멈췄을 때, 특정 변수나 표현식의 현재 값을 실시강 모니터링 가능
- 호출 스택(Call Stack) 창 : 현재 실행 위치에 도달하기 까지 호출된 함수의 순서를 보여줌
- 그 외에도 즉시 예외 검사, 실행 창, 프로세스에 연결 등의 기능도 존재



## E. 관련 단축키
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-nfnx{background-color:#E8E8E8;border-color:inherit;font-weight:bold;text-align:center;vertical-align:middle}
.tg .tg-rcip{background-color:#FFF;border-color:inherit;text-align:center;vertical-align:middle}
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