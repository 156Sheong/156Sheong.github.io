---
layout: single
title:  "소스 코드 편집기와 IDE 학습"
categories: Programming
tag: [Programming, TIL]
toc: true
sidebar:
    nav: "counts"
typora-root-url: ../
---



# 소스 코드 편집기(Source Code Editor)와 통합 개발 환경(Integrated Development Environment, IDE) 학습
- 학습 목표 : 소스 코드 편집기와 통합 개발 환경의 정의와 특징을 이해하고, 개인에 맞는 도구를 발견하는 것



## A. 문서 이력
- 최초 작성일 : 2025-11-18
- 최종 수정일 : 2025-11-21

- 작성 툴 : Typora, Visual Studio Code

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 온보딩 캠프 2일차 강의 내용 등



## B. 소스 코드 편집기 요약
- 소스 코드 편집기의 정의 : 프로그래머가 컴퓨터 프로그램의 소스 코드를 작성하고 수정하기 위해 사용하는 텍스트 편집기 프로그램

- 소스 코드 편집기의 주요 기능
  - 구문 강조(Syntax Highlighting): 코드의 각 요소(키워드, 주석, 변수 등)를 색상으로 구분해 가독성을 높임
  - 코드 자동 완성 : 코드 작성 중 다음에 올 수 있는 코드를 제안함
  - 자동 들여쓰기 : 코드의 구조를 자동으로 정렬함

- 소스 코드 편집기의 특징
  - 다양한 프로그래밍 언어를 사용 가능
  - 필요에 따라 플러그인과 확장 기능을 설치하여, 프로그래머가 원허는 대로 추가 기능 구현 가능
  - 톱합 개발 환경 보다 가벼움

- 소스 코드 편집기의 종류 및 장단점 
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-mzqp{background-color:#595959;font-weight:bold;text-align:center;vertical-align:middle}
.tg .tg-2g1l{background-color:#000000;font-weight:bold;text-align:center;vertical-align:middle}
.tg .tg-f4yw{background-color:#000000;text-align:center;vertical-align:middle}
</style>
<table class="tg"><thead>
  <tr>
    <th class="tg-mzqp">코드 편집기&nbsp;&nbsp;&nbsp;종류</th>
    <th class="tg-mzqp">특징</th>
    <th class="tg-mzqp">장점</th>
    <th class="tg-mzqp">단점</th>
    <th class="tg-mzqp">추천 대상</th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-2g1l">Visual Studio Code</td>
    <td class="tg-f4yw">마이크로소프트에서&nbsp;&nbsp;&nbsp;개발한 오픈 소스 코드 편집기</td>
    <td class="tg-f4yw">다양한&nbsp;&nbsp;&nbsp;OS 지원,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;디버깅, Git 통합 등 강력한 기능 내장,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;방대한 플러그인 생태계를 통한 광범위한 확장성,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;활발한 커뮤니티 및 지원</td>
    <td class="tg-f4yw">상대적으로&nbsp;&nbsp;&nbsp;무거움,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;JetBrains IDE보다는 리팩토링 기능이 다소 부족</td>
    <td class="tg-f4yw">웹&nbsp;&nbsp;&nbsp;개발자,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;프론트엔드 개발자,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;백엔드 개발자</td>
  </tr>
  <tr>
    <td class="tg-2g1l">Sublime Text</td>
    <td class="tg-f4yw">속도와&nbsp;&nbsp;&nbsp;효율성에 중점을 둔 경량 텍스트 편집기</td>
    <td class="tg-f4yw">매우&nbsp;&nbsp;&nbsp;빠름,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;대용량 파일 처리에도 안정적인 성능,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;직관적인 인터페이스</td>
    <td class="tg-f4yw">무료&nbsp;&nbsp;&nbsp;버전도 있으나 지속적인 사용을 위해서는 라이선스 구매 필요,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;디버깅 등 일부 기능은 플러그인 설치가 필수적</td>
    <td class="tg-f4yw">빠른&nbsp;&nbsp;&nbsp;속도를 선호하는 개발자,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;가벼운 소규모 프로젝트 개발자</td>
  </tr>
  <tr>
    <td class="tg-2g1l">Atom</td>
    <td class="tg-f4yw">GitHub에서&nbsp;&nbsp;&nbsp;개발한 웹 기술(Electron) 기반 오픈 소스 편집기</td>
    <td class="tg-f4yw">웹&nbsp;&nbsp;&nbsp;기술 기반의 다양한 사용자 정의 및 테마 설정 가능,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Git 및 GitHub와 연동이 강력함</td>
    <td class="tg-f4yw">다른&nbsp;&nbsp;&nbsp;편집기에 비해 다소 무겁고 느림,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;공식적인 신규 기능 개발은 중단</td>
    <td class="tg-f4yw">GitHub&nbsp;&nbsp;&nbsp;사용자</td>
  </tr>
  <tr>
    <td class="tg-2g1l">Notepad++</td>
    <td class="tg-f4yw">윈도우&nbsp;&nbsp;&nbsp;전용 무료 소스 코드 편집기</td>
    <td class="tg-f4yw">시스템&nbsp;&nbsp;&nbsp;리소스를 거의 사용하지 않는 극도의 가벼움</td>
    <td class="tg-f4yw">윈도우&nbsp;&nbsp;&nbsp;전용,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;다양한 플러그인이 있지는 않은 제한적 확장성,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;투박한 인터페이스</td>
    <td class="tg-f4yw">윈도우&nbsp;&nbsp;&nbsp;환경의 경량 작업을 처리하려는 개발자</td>
  </tr>
</tbody></table>



## C. 통합 개발 환경
- 통합 개발 환경의 정의 : 소프트웨어 개발에 필요한 모든 작업을 하나의 애플리케이션 안에서 처리할 수 있도록 다양한 도구를 통합해 제공하는 소프트웨어

- 통합 개발 환경의 주요 도구 및 기능
  - 소스 코드 편집기 : `B. 소스 코드 편집기`의 기능이 기본으로 포함됨
  - 컴파일러/언터프리터 : 작성된 소스 코드를 컴퓨터가 실행할 수 있도록 바이너리 코드로 변환해줌
  - 디버거(Debugger) : 코드 오류를 찾고 해결하는 데 도움을 줄 수 있는 기능
  - 빌드 자동화 도구 : 프로젝트를 빌드 및 패키징하는 과정을 자동화
  - 버전 관리 시스템(VCS) 통합 : Git 과 같은 버젼 관리 도구를 통합 개발 환경 내에서 직접 사용 가능함

- 통합 개발 환경의 특징
  - 특정 언어나 프레임워크에 최적화 됨 -> 대규모 프로젝트에서 개발자의 생산성 향상 가능
  - 다양한 기능이 포함되어 소스 코드 편집기 보다 상대적으로 무겁고, 시스템 자원 더 많이 소모할 수 있음
  
- 통합 개발 환경 종류 및 장단점
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-mzqp{background-color:#595959;font-weight:bold;text-align:center;vertical-align:middle}
.tg .tg-2g1l{background-color:#000000;font-weight:bold;text-align:center;vertical-align:middle}
.tg .tg-f4yw{background-color:#000000;text-align:center;vertical-align:middle}
</style>
<table class="tg"><thead>
  <tr>
    <th class="tg-mzqp">IDE 종류</th>
    <th class="tg-mzqp">특징</th>
    <th class="tg-mzqp">장점</th>
    <th class="tg-mzqp">단점</th>
    <th class="tg-mzqp">추천 대상</th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-2g1l">Visual Studio</td>
    <td class="tg-f4yw">마이크로소프트의&nbsp;&nbsp;&nbsp;강력한 IDE</td>
    <td class="tg-f4yw">디버깅,&nbsp;&nbsp;&nbsp;테스팅, UI 디자인 도구, 데이터베이스 관리 등 개발에 필요한 모든 기능 제공,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;강력한 윈도우 생태계에 통합되어 Azur, .NET 프레임워크와의 연동 뛰어남,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;다양한 코딩 도구 제공,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;다양한 언어 지원</td>
    <td class="tg-f4yw">높은&nbsp;&nbsp;&nbsp;리소스 사용,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;윈도우 중심이라 맥OS용 버전은 일부 기능이 제한될 수 있음</td>
    <td class="tg-f4yw">.NET/C#&nbsp;&nbsp;&nbsp;개발자,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;대규모 엔터프라이즈 프로젝트 개발자</td>
  </tr>
  <tr>
    <td class="tg-2g1l">JetBrains Rider</td>
    <td class="tg-f4yw">JetBrains의&nbsp;&nbsp;&nbsp;크로스 플랫폼 .NET IDE</td>
    <td class="tg-f4yw">대용량&nbsp;&nbsp;&nbsp;파일 처리 속도가 빠름,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;강력한 코드 분석 및 리펙토링,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;크로스 플랫폼 지원,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;유니티 및 언리얼 엔진 지원</td>
    <td class="tg-f4yw">유료&nbsp;&nbsp;&nbsp;소프트웨어,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;상대적으로 높은 메모리 사용량</td>
    <td class="tg-f4yw">.NET/Unity&nbsp;&nbsp;&nbsp;개발자,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;크로스 플랫폼 환경의 개발자</td>
  </tr>
  <tr>
    <td class="tg-2g1l">Android Studio</td>
    <td class="tg-f4yw">Google에서&nbsp;&nbsp;&nbsp;제공하는 안드로이드 앱 개발 공식 IDE.</td>
    <td class="tg-f4yw">안드로이드&nbsp;&nbsp;&nbsp;개발에 최적화,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Gradle 빌드 시스템 지원하여 복잡한 프로젝트 효율적으로 관리</td>
    <td class="tg-f4yw">안드로이드&nbsp;&nbsp;&nbsp;플랫폼 종속</td>
    <td class="tg-f4yw">안드로이드&nbsp;&nbsp;&nbsp;개발자</td>
  </tr>
  <tr>
    <td class="tg-2g1l">Eclipse</td>
    <td class="tg-f4yw">자바&nbsp;&nbsp;&nbsp;기반의 오픈 소스 IDE</td>
    <td class="tg-f4yw">광범위한&nbsp;&nbsp;&nbsp;플러그인 확장성,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;오랜 역사와 커뮤니티를 통한 풍부한 자료</td>
    <td class="tg-f4yw">느린&nbsp;&nbsp;&nbsp;성능,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;플러그인 간의 충돌 가능성 있음,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;투박한 인터페이스</td>
    <td class="tg-f4yw">JAVA&nbsp;&nbsp;&nbsp;개발자</td>
  </tr>
</tbody></table>                     |



## D. 주로 사용할 소스 코드 편집기 및 통합 개발 환경
- 사용할 소스 코드 편집기 : Visual Studio Code
  - 주요 용도 : Jekyll로 만들어진 GitHub Pages 블로그 글 작성 및 편집용
  - 선택 이유 : 초보 프로그래머가 처음 도전하기 가장 무난한 소스코드 편집기라 생각하여 정함

- 사용할 IDE : Visual Studio 2022
  - 주요 용도 : C# 콘솔, 유니티 C# 등 다용도 프로그래밍
  - 선택 이유 : 초보 프로그래머가 처음 도전하기 가장 무난한 IDE라 생각하여 정함, 온보딩 캠프에서도 추천함
    - Visual Studio 2026을 사용하지 않는 이유 : Visual Studio 2026이 최신 기능을 제공할 수 있으나, 안정성과 레거시 시스템 지원에서 이슈가 있을 수도 있을 것 같아서 한 동안 Visual Studio 2022를 사용할 예정