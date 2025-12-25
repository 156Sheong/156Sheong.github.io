---
layout: single
title:  "연산자 학습"
categories: TIL
tag: [Programming, TIL, CSharp]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 연산자(Operator) 학습
- 학습 목표 : C#에서 활용 가능한 연산자와 우선순위를 이해하고 사용법을 숙지하는 법



## A. 문서 이력
- 최초 작성일 : 2025-11-20
- 최종 수정일 : 2025-12-10

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 온보딩 캠프 4일차 및 본과정 2일차 강의 내용, [MSDN C# 대입 연산자 문서](https://learn.microsoft.com/ko-kr/dotnet/csharp/language-reference/operators/assignment-operator), [MSDN C# 부울 논리 연산자 문서](https://learn.microsoft.com/ko-kr/dotnet/csharp/language-reference/operators/boolean-logical-operators) 등



## B. 연산자의 정의
  - 어떤 논리 체계 안에서 연산을 수행할 때, 연산의 역할을 하는 기호를 연산자라고 함
  - 프로그래밍 언어는 수학 연산과 유사한 연산자를 지원
  - 각 프로그래밍 언어마다 연산자의 의미나 기호는 다를 수 있음
  - 일부 프로그래밍 언어는 프로그래머가 정의한 연산자의 생성을 허용할 수 있음



## C. 연산자의 종류
- 연산자는 산술, 관계, 논리, 할당, 비트 및 기타 연산자 등으로 구분 가능

### Ca. 산술 연산자 (Arithmetic Operators)
  - 숫자 값에 대한 기본적인 수학 연산 수행
  - `+`
    - 두 피연산자의 값을 더함
    - a + b
  - `-`
    - 두 피연산자의 값을 뺌
    - a - b 
  - `*`
    - 두 피연산자의 값을 곱합
    - a * b
  - `/`
    - 두 피연산자의 값을 나누고 몫을 반환함
    - 정수형 피연산자끼리 연산하면 정수형 값이 나오는 것을 주의
    - a / b
  - `%`
    - 두 피연산자의 값을 나누고 나머지를 반환함
    - a % b

### Cb. 대입 연산자 (할당 연산자, Assignment Operators)
  - 오른쪽 피연산자의 값을 왼쪽 피연산자가 제공하는 변수, 속성 등에 할당
  - 복합 할당 연산자로서, 산술 연산자, 논리 연산자, 비트 연산자 등과 함께 사용 가능
  - `=`
    - 왼쪽 피연산자의 값을 우측 피연산자의 값으로 할당함
    - a = b
  - `+=`, `-=`, `*=`, `/=`, `%=`
    - 산술 연산자와 결합한 복합 할당 연산자
    - a += b : a의 기존의 값에 b를 더함
  - `&=`, `|=`, `^=`, `<<=`, `>>=`
    - 비트 연산자와 결합한 복합 할당 연산자

### Cc. 관계 연산자 (Relational/Comparison Operators)
  - 두 피연산자 간의 관계를 비교해 true / false 반환
  - `==`
    - 두 피연산자의 값이 같음
    - a == b
  - `!=`
    - 두 피연산자의 값이 같지 않음
    - a != b
  - `>`
    - 좌측 피연산자의 값이 우측 피연산자의 값보다 큼
    - a > b
  - `<`
    - 좌측 피연산자의 값이 우측 피연산자의 값보다 작음
    - a < b
  - `>=`
    - 좌측 피연산자의 값이 우측 피연산자의 값보다 크거나 같음
    - a >= b
  - `<=`
    - 좌측 피연산자의 값이 우측 피연산자의 값보다 작거나 같음
    - a <= b

### Cd. 증감 연산자 (Increment/Decrement Operators)
  - 피연사자의 값을 1증감시키는 연산자
    - a++(후위 연산자), ++a(전위 연산자) 의 형태로 활용 가능
    - 전위 연산과 후위 연산의 결과 값 차이가 있을 수 있으니 주의 필요
  - `++`
    - 피연산자의 값 1증가
    - ++a, a++
  - `--` 
    - 피연산자의 값 1감소
    - --a, a--

### Ce. 논리 연산자 (Logical Operators)
  - bool 피연산자를 사용하여 논리 연산을 수행 후, true / false 반환
  - [논리 연산자와 조건문 포스트](https://156sheong.github.io/programming/Logical_Operator/) 참고

### Cf. 비트 연산자 (Bitwise Operators)
  - 정수 형식의 피연산자에 대해 비트 단위로 연산을 수행
  - `&`
    - 비트 AND
  - `|`
    - 비트 OR
  - `^`
    - 비트 XOR : 두 개의 비트를 비교하여, 두 비트가 서로 다를 경우에만 1을 반환, 같으면 0을 반환
  - `~`
    - 비트 NOT (보수) : 피연산자의 각 비트를 반전시키는 단항 연산자. 즉, 0은 1로, 1은 0으로 바꿈
  - `<<`
    - 왼쪽 시프트 : 피연산자의 비트들을 지정된 횟수만큼 왼쪽으로 이동
  - `>>`
    - 오른쪽 시프트 : 피연산자의 비트들을 지정된 횟수만큼 오른쪽으로 이동

### Cg. 기타 주요 연산자
  - `?` : 삼항 연산자
    - 조건(조건식), 참일 때의 결과, 거짓일 때의 결과라는 세 개의 피연산자를 가지는 조건 연산자
    - if-else 문을 더 간결하게 표현할 수 있게 해주는 문법
    - `(조건)` ? `참일 때 값` : `거짓일 때 값` 형식으로 사용
      - (a == b) ? true : false
  - `is` : is 연산자 - 객체가 특정 형식의 인스턴스인지 확인
  - `as` : as 연산자 - 호환되는 형식 간 형 변환을 시도, 실패 시 null을 반환
  - `typeof` : typeof 연산자 - 형식의 System.Type 객체를 가져옴
  - `new` : new 연산자 - 새 객체나 배열을 만듬


## D. 연산자 우선순위
- 위에서 아래로 갈수록 우선순위가 점차 낮아짐
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-bc6i{background-color:#329a9d;border-color:inherit;color:#ffffff;font-weight:bold;text-align:center;vertical-align:top}
.tg .tg-us1l{background-color:#003532;border-color:inherit;color:#ffffff;font-weight:bold;text-align:center;vertical-align:top}
.tg .tg-0paf{background-color:#329a9d;border-color:inherit;color:#ffffff;text-align:center;vertical-align:top}
</style>
<table class="tg"><thead>
  <tr>
    <th class="tg-us1l">카테고리</th>
    <th class="tg-us1l">연산자</th>
    <th class="tg-us1l">설명</th>
    <th class="tg-us1l">결합성</th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-bc6i">기본</td>
    <td class="tg-0paf">x.y, f(x), a[x], x++, x--, new, typeof, checked, unchecked, default, delegate, sizeof, -&gt;</td>
    <td class="tg-0paf">멤버 접근, 함수 호출, 인덱싱,   후위 증감, 생성 등</td>
    <td class="tg-0paf">왼쪽에서 오른쪽</td>
  </tr>
  <tr>
    <td class="tg-bc6i">단항</td>
    <td class="tg-0paf">+, -, !, ~, ++x, --x, (T)x, *, &amp;</td>
    <td class="tg-0paf">단항 덧셈/뺄셈, 논리/비트 NOT,   전위 증감, 형 변환, 포인터 등</td>
    <td class="tg-0paf">오른쪽에서 왼쪽</td>
  </tr>
  <tr>
    <td class="tg-bc6i">곱하기</td>
    <td class="tg-0paf">*, /, %</td>
    <td class="tg-0paf">곱셈, 나눗셈, 나머지</td>
    <td class="tg-0paf">왼쪽에서 오른쪽</td>
  </tr>
  <tr>
    <td class="tg-bc6i">덧셈</td>
    <td class="tg-0paf">+, -</td>
    <td class="tg-0paf">덧셈, 뺄셈</td>
    <td class="tg-0paf">왼쪽에서 오른쪽</td>
  </tr>
  <tr>
    <td class="tg-bc6i">시프트</td>
    <td class="tg-0paf">&lt;&lt;, &gt;&gt;</td>
    <td class="tg-0paf">비트 왼쪽/오른쪽 시프트</td>
    <td class="tg-0paf">왼쪽에서 오른쪽</td>
  </tr>
  <tr>
    <td class="tg-bc6i">관계 및 형식 테스트</td>
    <td class="tg-0paf">&lt;, &gt;, &lt;=, &gt;=, is, as</td>
    <td class="tg-0paf">비교, 형식 검사</td>
    <td class="tg-0paf">왼쪽에서 오른쪽</td>
  </tr>
  <tr>
    <td class="tg-bc6i">같음</td>
    <td class="tg-0paf">==, !=</td>
    <td class="tg-0paf">같음, 같지 않음</td>
    <td class="tg-0paf">왼쪽에서 오른쪽</td>
  </tr>
  <tr>
    <td class="tg-bc6i">비트 AND</td>
    <td class="tg-0paf">&amp;</td>
    <td class="tg-0paf">비트 AND</td>
    <td class="tg-0paf">왼쪽에서 오른쪽</td>
  </tr>
  <tr>
    <td class="tg-bc6i">비트 XOR</td>
    <td class="tg-0paf">^</td>
    <td class="tg-0paf">비트 XOR</td>
    <td class="tg-0paf">왼쪽에서 오른쪽</td>
  </tr>
  <tr>
    <td class="tg-bc6i">비트 OR</td>
    <td class="tg-0paf">`</td>
    <td class="tg-0paf">`</td>
    <td class="tg-0paf">비트 OR</td>
  </tr>
  <tr>
    <td class="tg-bc6i">논리 AND</td>
    <td class="tg-0paf">&amp;&amp;</td>
    <td class="tg-0paf">논리 AND</td>
    <td class="tg-0paf">왼쪽에서 오른쪽</td>
  </tr>
  <tr>
    <td class="tg-bc6i">논리 OR</td>
    <td class="tg-0paf">`</td>
    <td class="tg-0paf">　</td>
    <td class="tg-0paf">`</td>
  </tr>
  <tr>
    <td class="tg-bc6i">Null 병합</td>
    <td class="tg-0paf">??</td>
    <td class="tg-0paf">Null 병합</td>
    <td class="tg-0paf">오른쪽에서 왼쪽</td>
  </tr>
  <tr>
    <td class="tg-bc6i">조건(삼항)</td>
    <td class="tg-0paf">?:</td>
    <td class="tg-0paf">삼항 조건 연산자</td>
    <td class="tg-0paf">오른쪽에서 왼쪽</td>
  </tr>
  <tr>
    <td class="tg-bc6i">할당 및 람다</td>
    <td class="tg-0paf">=, *=, /=, %=, +=, -=, &lt;&lt;=, &gt;&gt;=, &amp;=, ^=,   `</td>
    <td class="tg-0paf">=, =&gt;`</td>
    <td class="tg-0paf">할당 연산자 및 람다</td>
  </tr>
</tbody></table>



## E. 연산 시 주의사항
- C#, Java 등 컴퓨터 언어는 정확히 소수점을 표현할 수 없어서 실수형의 소수점 연산 시에 오차가 존재함, 부동소수점의 이진수를 십진수로 제대로 표현하기 어렵기 때문
  - flaot(4바이트) 보다 정밀한 계산이 필요하면 decimal(C#에서 16바이트 십진법), double(8바이트 이진법) 등을 추천
  - [CS 기초 학습 - 2 포스트](https://156sheong.github.io/programming/TIL_CS_Basic02/) 참고



## E. 더 생각해보기
- C#에서 내부적으로 a = a + 1; 와 a += 1; 와 a++; 는 컴파일 과정에서 아예 동일한 방식으로 연산을 할까, 아니면 내부적으로는 약간 다른 방식일까
- **답변**
  - 내부적으로 같은 방식으로 처리되지는 않음, 그러나 큰 차이는 없고, 이를 까보려고 하면 저레벨 언어까지 뜯어봐야함, (추후 연구해볼만한 주제)