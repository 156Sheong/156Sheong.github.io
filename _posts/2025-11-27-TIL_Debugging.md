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

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 온보딩 캠프 9일차 강의 내용, [마이크로소프트 Learn 디버거 설명](https://learn.microsoft.com/ko-kr/visualstudio/debugger/debugger-feature-tour?view=visualstudio), [유니티 매뉴얼 프로파일러 설명](https://docs.unity3d.com/kr/2019.3/Manual/ProfilerCPU.html) 등



## B. 디버깅



### Ba. 디버깅의 정의
- 코드가 예상대로 작동하지 않을 때, 코드 내 버그를 식별하고, 위치를 찾아내며, 수정하는 과정
- 비주얼 스튜디오의 경우 통합 디버거를 활용해 버그를 빠르게 찾아낼 수 있음



### Bb. 디버깅 과정 및 방법
1. 문제 재현 : 버그가 발생한 특정 시나리오나 입력값을 찾음
2. 격리 및 분석
   - 비주얼 스튜디오 디버거 등을 사용하여 프로그램 실행을 중단, 버그가 발생한 코드 영역을 격리함
   - 변수 값, 호출 스택, 메모리 상태 등 검사해 원인을 분석
3. 가설 수립 및 수정 : 문제의 근본 원인에 대한 가설을 세우고 코드를 수정해 문제를 해결
4. 검증 및 회귀 테스트
    - 수정된 코드를 실행해 버그가 해결되었는지 확인
    - 새로운 버그가 발생하지 않도록 관련 테스트 수행



### Bc. 비주얼 스튜디오의 주요 디버깅 도구 및 기술
- 중단점(Breakpoints) : 코드의 특정 줄에서 프로그램 실행을 일시 중지함
- 조사식(Watch) 창 / 자동(Autos) 창 / 지역(Locals) 창 : 중단점에서 멈췄을 때, 특정 변수나 표현식의 현재 값을 실시강 모니터링 가능
- 호출 스택(Call Stack) 창 : 현재 실행 위치에 도달하기 까지 호출된 함수의 순서를 보여줌
- 그 외에도 즉시 예외 검사, 실행 창, 프로세스에 연결 등의 기능도 존재



### Bd. 비주얼 스튜디오의 디버깅 관련 단축키
<style type="text/css">
.tg  {border-collapse:collapse;border-color:#93a1a1;border-spacing:0;}
.tg td{background-color:#fdf6e3;border-color:#93a1a1;border-style:solid;border-width:1px;color:#002b36;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#657b83;border-color:#93a1a1;border-style:solid;border-width:1px;color:#fdf6e3;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-sutj{background-color:#1f5059;border-color:inherit;color:#ffffff;text-align:center;vertical-align:middle}
.tg .tg-wf0n{background-color:#1f5059;border-color:inherit;color:#ffffff;text-align:left;vertical-align:top}
.tg .tg-udfd{background-color:#2f414a;border-color:inherit;color:#ffffff;font-weight:bold;text-align:center;vertical-align:middle}
.tg .tg-mr47{background-color:#1f5059;border-color:inherit;color:#ffffff;text-align:left;vertical-align:middle}
.tg .tg-0paf{background-color:#1f5059;border-color:inherit;color:#ffffff;text-align:center;vertical-align:top}
</style>
<table class="tg"><thead>
  <tr>
    <th class="tg-udfd">단축키</th>
    <th class="tg-udfd">설명</th>
    <th class="tg-udfd">기능 상세</th>
  </tr></thead>
<tbody>
  <tr>
    <td class="tg-sutj">F5</td>
    <td class="tg-sutj">디버깅 시작</td>
    <td class="tg-mr47">디버거와 함께 프로그램 실행 시작, 다음 중단점까지 실행</td>
  </tr>
  <tr>
    <td class="tg-sutj">Shift + F5</td>
    <td class="tg-sutj">디버깅 중지</td>
    <td class="tg-mr47">현재 디버깅 세션을 종료</td>
  </tr>
  <tr>
    <td class="tg-sutj">F9</td>
    <td class="tg-sutj">중단점 설정 /해제</td>
    <td class="tg-mr47">현재 커서가 있는 줄에 중단점을 설정하거나 해제</td>
  </tr>
  <tr>
    <td class="tg-sutj">F10</td>
    <td class="tg-sutj">한 단계 프로시저 단위 실행</td>
    <td class="tg-mr47">현재 줄을 실행하고 다음 줄로 이동. 함수 내부로 들어가지 않고(Step Over), 함수 전체 실행 후 다음 줄로 이동</td>
  </tr>
  <tr>
    <td class="tg-sutj">F11</td>
    <td class="tg-sutj">한 단계씩 코드 실행</td>
    <td class="tg-mr47">현재 줄을 실행하고 다음 줄로 이동. 함수 내부로 진입(Step Into)하여 자세히 디버깅</td>
  </tr>
  <tr>
    <td class="tg-sutj">Shift + F11</td>
    <td class="tg-sutj">한 단계 프로시저 나가기</td>
    <td class="tg-mr47">현재 함수 실행을 완료하고 해당 함수를 호출한 위치로 돌아감(Step Out)</td>
  </tr>
  <tr>
    <td class="tg-0paf">Ctrl + F10</td>
    <td class="tg-0paf">커서까지 실행</td>
    <td class="tg-wf0n">커서가 위치한 곳까지 프로그램 실행을 계속</td>
  </tr>
  <tr>
    <td class="tg-0paf">F1</td>
    <td class="tg-0paf">도움말</td>
    <td class="tg-wf0n">특정 키워드나 메뉴에 대한 도움말 확인</td>
  </tr>
</tbody></table>



## C. 유니티 프로파일러



### Ca. 유니티 프로파일러의 정의
- 유니티 엔진으로 개발 중인 애플리케이션의 성능 정보를 수집하고 분석하는 성능 분석 도구
- 애플리케이션 실행 중 CPU, GPU, 메모리, 랜더링, 오디오 등 다양한 영역에서 시간이 얼마나 소요되는지 차트로 표시하여 성능 병목 현상(bottleneck)을 식별하고 최적화 할 수 있도록 도움



### Cb. 유니티 프로파일러의 주요 구성 요소 (Profiler Modules)
- CPU Usage (CPU 사용량) : 애플리케이션이 각 프레임에 소비하는 시간에 대한 포괄적 정보 제공, 스크립트 실행, 물리 엔진, 가비지 컬렉션(GC), 애니메이션 등 다양한 작업에 소요되는 시간을 계층 구조나 타임라인 형태로 보여줌
- GPU Usage (GPU 사용량) : 렌더링 작업에 대한 성능 데이터를 표시, GPU 관련 병목 현상을 식별하는 데 사용
- Memory (메모리) : 애플리케이션의 메모리 사용량에 대한 정보를 제공, 각 에셋이 얼마나 많은 메모리를 차지하는지, 메모리 누수(Memory Leak)가 있는지 확인 가능
- Rendering (렌더링) : 렌더링 통계, 화면 해상도, 초당 프레임 수, 배치(Batching) 정보 등을 상세히 표시함
- Audio (오디오) : 현재 재생 중인 오디오 소스 수, 오디오 로드 시간 등 오디오 시스템의 성능 부하를 모니터링함
- Physics/Physics 2D (물리/2D 물리) : 물리 계산에 소요되는 시간을 보여주어, 과도한 물리 연산을 최적화 할 수 있도록 도움



### Cc. 유니티 프로파일러의 사용법
1. 프로파일러 열기 : 유니티 에디터 상단 메뉴에서 Window > Analysis > Profiler를 선택 or 단축키 Ctrl + 7 (macOS: Cmd + 7)
2. 프로파일링 대상 설정
   - 에디터의 플레이 모드(Play Mode)에 들어가서 테스트 및 데이터 실시간 확인 가능
   - 실제 기기를 연결하여 Development Build 옵션을 활성화하여 빌드하고, 해당 기기를 연결해 테스트 및 데이터 실시간 확인 가능
3. 데이터 분석 : 타임라인 차트나, 상세 정보 패널에서 성능 스파이크, 상세한 계층적 데이터 확인 가능