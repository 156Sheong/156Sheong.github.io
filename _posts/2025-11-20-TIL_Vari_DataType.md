---
layout: single
title:  "변수 및 자료형 학습 (추가 내용 추가 필요)"
categories: Programming
tag: [Programming, TIL, CSharp]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 변수(Variable)와 자료형(Data Type) 학습
- 학습 목표 : C#에서 활용 가능한 주요 변수의 개념과 실제 사용 방법을 이해하는 것



## A. 문서 이력
- 최초 작성일 : 2025-11-20
- 최종 수정일 : 2025-12-09

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 온보딩 캠프 3일차 및 본과정 2일차 강의 내용, [마이크로소프트 C# 기본 제공 형식 문서](https://learn.microsoft.com/ko-kr/dotnet/csharp/language-reference/builtin-types/built-in-types) 등



(변수가 필요한 이유 추가 필요)
(변수 사용법 저장하고자 하는 형태, 저장소 이름, 실제 값 내용 추가 필요)
(컴퓨터적으로 사고한다면 일단 선언된 변수의 값도 컴파일러를 거쳐서 값 형태로 주소 메모리에 이진수의 형태로 들어감)


## B. 변수와 상수 설명
- 변수와 상수는 값을 저장하기 위한 이름이 있는 메모리 공간
- 변수와 상수는 특정 자료형(Data Type) 가짐
  
- **변수(Variable)**
  - 프로그램이 실행되는 동안 값이 변경될 수 있는 메모리 공간
  - 변수 안에 저장된 값은 언제든지 변경될 수 있음
  
- **상수(constant)**
  - 한 번 할당되면 프로그램 실행 중 절대 변경할 수 없는 값(변경하려고 시도하면 오류 발생)
  - 변수 선언 시, 변수명 앞에 const 를 붙이고, 선언할 때 초기화도 해야함
  - 예시 : const int maxHP = 100;
  - 상수는 게임에서 바뀌지 않을 값을 만들 때 가끔 사용됨



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
.tg .tg-7vxo{background-color:#34696D;color:#FFF;text-align:left;vertical-align:top}
.tg .tg-8bs2{background-color:#003532;color:#FFF;font-weight:bold;text-align:center;vertical-align:top}
</style>
<table class="tg"><thead>
  <tr>
    <th class="tg-8bs2"><span style="font-weight:bold;color:#FFF;background-color:#003532">자료형</span></th>
    <th class="tg-8bs2"><span style="font-weight:bold;color:#FFF;background-color:#003532">설명</span></th>
    <th class="tg-8bs2"><span style="font-weight:bold;color:#FFF;background-color:#003532">예시</span></th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">string</span></td>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">문자 를 저장, 큰따옴표로 묶음.</span></td>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">string s = "Hello World";</span></td>
  </tr>
  <tr>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">object</span></td>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">모든 C# 형식의 부모 클래스로, 모든 데이터를 저장 가능</span></td>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">object o = 10;</span></td>
  </tr>
  <tr>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">class</span></td>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">사용자 정의 데이터 구조를 만듬</span></td>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">MyClass mc = new MyClass();</span></td>
  </tr>
  <tr>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">array, List</span>&lt;/td&gt;</td>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">순서가 있는 데이터의 집합을 저장, 시퀀스형</span></td>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">int[] arr = { 1, 2, 3 };</span><br><span style="color:#FFF;background-color:#34696D">List</span> list = new List();&lt;/td&gt; &lt;/tr&gt;</td>
  </tr>
  <tr>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">Dictionary&lt;TKey, TValue&gt;</span></td>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">Key와 Value의 쌍으로 데이터를 저장, 매핑형</span></td>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">Dictionary&lt;string, int&gt; dict = new Dictionary&lt;string, int&gt;();</span></td>
  </tr>
  <tr>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">interface, array, delegate</span></td>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">다른 복합적인 데이터 구조 및 기능을 정의하는 데 사용</span></td>
    <td class="tg-7vxo"><span style="color:#FFF;background-color:#34696D">　</span></td>
  </tr>
</tbody></table>



## C. 변수 선언과 값 대입 주요 규칙
- 컴퓨터는 코드를 메인이라는 시작점의 중괄호부터 읽기 시작
- 변수를 저장할 목적의 공간 확보 코드(변수 선언)가 나오면 요청된 공간만큼 자리 확보
- 특정 수를 변수에 대입하라는 코드를 만나면 식별자를 보고 그 공간으로 가서 값 대입
- 변수 선언과 동시에 값을 대입(변수 초기화) 가능



## D. 변수명 규칙
- **파스칼 케이스(PascalCase)**
  - 단어의 첫 글자를 포함해 모든 단어의 첫 글자를 대문자로표기
  - 사용 예시
    - `클래스(Class)` : public class DamageCalculator
    - `메서드(Method)` : public void CalculateTotalPrice ()
    - `속성(Property)` : public string UserName {get; set;}
    - `열거형(Enum)` : public enum GameLevel {Easy, Normal, Hard}
    - `네임스페이스(Namespace)` : namespace MyApplication.Services
    - `구조체(Struct)` : public struct Point

- **카멜 케이스(camelCase)**
  - 첫 단어의 첫 글자는 소문자로, 이후 단어의 첫 글자는 대문자로 표기
  - 사용 예시
    - `매개 변수(Parameter)` : public int HPCalculator (int dmg, int curentHP)
    - `지역 변수(Local Variable)` : int maxRate - 100000;
    - `전용 필드(Private Field)` : privatestring _customerName;



## E. 변수명 짓기 팁
- 변수가 무엇을 의미하는 지 이름만 봐도 알 수 있게 만들기
- 널리 알려진 약어(HP, ATK 등)이 아니라면 축약어는 최대한 피하기
- 변수의 구현보다는 의도를 담아내기
- 변수명 규칙을 일관되게 사용하기
- 변수는 주로 명사나 명사형 형용사를 활용하고, 메서드는 동사형을 활용하기
- for 문, while 문 등의 **스코프(Scope)** 내 변수는 i, j, k 등의 짧은 변수명을 사용해도 됨



 ## F. 더 생각해보기
- 의문 1
  - Bool(Boolean) 이 true 와 false 값만 가진다면 C#에서 1bit 의 값이면 될 것 같은데, 실제로는 1byte의 값을 가지는 이유가 무엇인가?
  - 확인한 사항 : 컴퓨터는 바이트 단위를 사용하는데 혼자 비트 단위를 사용하면 오히려 비효율적이기 때문
- 의문 2
  - float, double, decimal 같은 실수 자료형이 unsigned가 없는 이유가 무엇일까?
  - 현재 확인한 사항 : [IEEE 754 규칙](https://ko.wikipedia.org/wiki/IEEE_754) 으로 정해졌기 때문
  - 재의문 : 규칙이란건 언제나 불변한 것은 아니고 시대나 상황이 바뀌면 바뀔 수 있는 것이니 필요하다면 누군가 이미 만들었을 것인데, 실수 자료형은 unsigned가 필요한 상황이 많이 없는 것인가?
  - 나의 가정
    - 만약 unsigned가 되어 최대 값이 양의 정수로 표현할 수 있는 범위가 2배가 된다고 해도 부동 소수점의 오차는 계속 존재하니, 오차가 있는 매우 높은 자리수의 실수 값은 차라리 소수점을 버리고 정수형으로 표시하는게 오히려 오차가 더 적을 것
    - 또한, 소수점 이하로 매우 낮은 자리수의 소수도 부동 소수점 오차가 커지니 unsigned 실수형을 새로 정의 할만큼 활용처 많을 것 같지는 않은 것
    - 그러니 IEEE 754 를 보면 부동 소수점 하나 만들 때도 규칙이 매우 길고 복잡한데, 여기에 unsigned 붙인 실수 자료형 하나 더 만들고 전세계 컴퓨터의 각종 운영체제와 응용 프로그램 등에 작동 방법을 넣어서 표준화 시키려면 필요한 코스트가 많을 것 같은데 그에 비해 얻는 메리트는 크지 않다고 느껴짐





 <!-- 추후 추가할지 고민중

형변환 추가 필요


  - var 키워드
    - 자동으로 자료형을 추론해주는 키워드
    - 컴파일 시 정확한 타입이 정해짐
    - 명시적인 자료형이랑 런타임 성능 차이는 없음
    - 가독성을 해칠 수 있음
      -  가독성과 명확성을 해치지 않는 선에서 적절히 사용해야
    - 잘못된 추론의 가능성 있음





자리표시자와 문자열 보간이 내부적으로는 메모리나 연산 속도 등의 차이가 있을까요??
-> 버젼마다의 차이가 있는데 C# 10.0 이후에는 문자열 보간이 더 빠름, 그러나 거의 차이가 없음



 
 	
C#에서 int형 데이터를 계산할 때 잠시 float로 형변환 하는 거랑,
처음부터 float형 데이터로 선언하고 계산하는 거랑 메모리나 연산 속도에 유의미한 차이가 있을까요?
온보딩 과정 때 알게 된 코딩 테스트의 다른 사람 풀이를 보면,
형변환을 하는 경우가 많은 것 같아서 여쭤봅니다.
-> 둘다 값타입이고 4바이트라서 유의미한 차이가 없음, 값타입과 참조타입의 차이라면 연산 차이가 클 것



-->


