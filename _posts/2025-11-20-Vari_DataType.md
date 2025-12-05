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

### Ba. 값 형식 (Value Types)
- 값 형식 자료형의 변수는 데이터를 집적 저장
- 주로 기본 제공 형식(built-in types)이 속함

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-zdbk{background-color:#003532;color:#ffffff;font-weight:bold;text-align:center;vertical-align:top}
.tg .tg-vg0y{background-color:#34696d;color:#ffffff;text-align:left;vertical-align:top}
</style>
<table class="tg"><thead>
  <tr>
    <th class="tg-zdbk">자료형</th>
    <th class="tg-zdbk">크기</th>
    <th class="tg-zdbk">설명</th>
    <th class="tg-zdbk">예시</th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-vg0y">byte</td>
    <td class="tg-vg0y">1 byte</td>
    <td class="tg-vg0y">부호 없는 짧은 정수 (0 ~ 255)</td>
    <td class="tg-vg0y">byte   bt = 200;</td>
  </tr>
  <tr>
    <td class="tg-vg0y">int</td>
    <td class="tg-vg0y">4   bytes</td>
    <td class="tg-vg0y">부호 있는   정수 (-21억 ~ 21억)</td>
    <td class="tg-vg0y">int i   = 100;</td>
  </tr>
  <tr>
    <td class="tg-vg0y">uint</td>
    <td class="tg-vg0y">4   bytes</td>
    <td class="tg-vg0y">부호 없는 정수 (0 ~ 42억)</td>
    <td class="tg-vg0y">uint   i = 1000000;</td>
  </tr>
  <tr>
    <td class="tg-vg0y">long</td>
    <td class="tg-vg0y">8   bytes</td>
    <td class="tg-vg0y">부호 있는 긴 정수 (-922경   ~ 922경)</td>
    <td class="tg-vg0y">long l   = 1234567890123L;</td>
  </tr>
  <tr>
    <td class="tg-vg0y">ulong</td>
    <td class="tg-vg0y">8   bytes</td>
    <td class="tg-vg0y">부호 없는 긴 정수 (0 ~ 1844경)</td>
    <td class="tg-vg0y">long   l = 1234567890123L;</td>
  </tr>
  <tr>
    <td class="tg-vg0y">float</td>
    <td class="tg-vg0y">4   bytes</td>
    <td class="tg-vg0y">단정밀도   부동 소수점 실수 (소수점 7자리)</td>
    <td class="tg-vg0y">float   f = 10.2f;</td>
  </tr>
  <tr>
    <td class="tg-vg0y">double</td>
    <td class="tg-vg0y">8   bytes</td>
    <td class="tg-vg0y">배정밀도   부동 소수점 실수 (소수점 15자리)</td>
    <td class="tg-vg0y">double   d = 19.99;</td>
  </tr>
  <tr>
    <td class="tg-vg0y">decimal</td>
    <td class="tg-vg0y">16   bytes</td>
    <td class="tg-vg0y">금융 계산   등에 사용되는 높은 정밀도의 실수</td>
    <td class="tg-vg0y">decimal   money = 12.5m;</td>
  </tr>
  <tr>
    <td class="tg-vg0y">char</td>
    <td class="tg-vg0y">2   bytes</td>
    <td class="tg-vg0y">단일 문자   (UTF-16 유니코드 문자)</td>
    <td class="tg-vg0y">char c   = 'A';</td>
  </tr>
  <tr>
    <td class="tg-vg0y">bool</td>
    <td class="tg-vg0y">1 byte</td>
    <td class="tg-vg0y">논리값 (true 또는 false)</td>
    <td class="tg-vg0y">bool b   = true;</td>
  </tr>
</tbody></table>


### Bb. 참조 형식 (Reference Types)
- 참조 형식 자료형의 변수는 실제 데이터가 저장된 메모리 주소(참조)를 저장함

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-zdbk{background-color:#003532;color:#ffffff;font-weight:bold;text-align:center;vertical-align:top}
.tg .tg-vg0y{background-color:#34696d;color:#ffffff;text-align:left;vertical-align:top}
</style>
<table class="tg"><thead>
  <tr>
    <th class="tg-zdbk">자료형       </th>
    <th class="tg-zdbk">설명</th>
    <th class="tg-zdbk">예시</th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-vg0y">string</td>
    <td class="tg-vg0y">문자 를 저장, 큰따옴표로 묶음.</td>
    <td class="tg-vg0y">string   s = "Hello World";</td>
  </tr>
  <tr>
    <td class="tg-vg0y">object</td>
    <td class="tg-vg0y">모든 C# 형식의 부모 클래스로, 모든 데이터를 저장 가능</td>
    <td class="tg-vg0y">object   o = 10;</td>
  </tr>
  <tr>
    <td class="tg-vg0y">class</td>
    <td class="tg-vg0y">사용자 정의 데이터 구조를 만듬</td>
    <td class="tg-vg0y">MyClass   mc = new MyClass();</td>
  </tr>
  <tr>
    <td class="tg-vg0y">array, List<T></td>
    <td class="tg-vg0y">순서가 있는 데이터의 집합을 저장, 시퀀스형</td>
    <td class="tg-vg0y">int[] arr = { 1, 2, 3 };<br>List<string> list = new List<string>();</td>
  </tr>
    <tr>
    <td class="tg-vg0y">Dictionary<TKey, TValue></td>
    <td class="tg-vg0y">Key와 Value의 쌍으로 데이터를 저장, 매핑형</td>
    <td class="tg-vg0y">Dictionary<string, int> dict = new Dictionary<string, int>();</td>
  </tr>
    <tr>
    <td class="tg-vg0y">interface, array, delegate</td>
    <td class="tg-vg0y">다른 복합적인 데이터 구조 및 기능을 정의하는 데 사용</td>
    <td class="tg-vg0y">　</td>
  </tr>
</tbody>
</table>



## C. 변수 선언과 값 대입 주요 규칙
- 컴퓨터는 코드를 메인이라는 시작점의 중괄호부터 읽기 시작
- 변수를 저장할 목적의 공간 확보 코드(변수 선언)가 나오면 요청된 공간만큼 자리 확보
- 특정 수를 변수에 대입하라는 코드를 만나면 식별자를 보고 그 공간으로 가서 값 대입
- 변수 선언과 동시에 값을 대입(변수 초기화) 가능



## D. 변수명 규칙
- **파스칼 케이스(PascalCase)**
  - 단어의 첫 글자를 포함해 모든 단어의 첫 글자를 대문자로표기
  - 사용 예시
    - 클래스(Class) : public class DamageCalculator
    - 메서드(Method) : public void CalculateTotalPrice ()
    - 속성(Property) : public string UserName {get; set;}
    - 열거형(Enum) : public enum GameLevel {Easy, Normal, Hard}
    - 네임스페이스(Namespace) : namespace MyApplication.Services
    - 구조체(Struct) : public struct Point

- **카멜 케이스(camelCase)**
  - 첫 단어의 첫 글자는 소문자로, 이후 단어의 첫 글자는 대문자로 표기
  - 사용 예시
    - 매개 변수(Parameter) : public int HPCalculator (int dmg, int curentHP)
    - 지역 변수(Local Variable) : int maxRate - 100000;
    - 전용 필드(Private Field) : privatestring _customerName;