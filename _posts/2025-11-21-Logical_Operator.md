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

- 정보 출처 : 경일게임IT아카데미 프로그래밍 4기 - 온보딩 캠프 5일차 강의 내용 등



## B. 논리 연산자에 대하여
- 둘 이상의 조건식 또는 불 값을 결합해 단일의 참 / 거짓 결과를 반환한느데 사용되는 연산자
- 논리 연산자의 종류
% Please add the following required packages to your document preamble:
% \usepackage[table,xcdraw]{xcolor}
% Beamer presentation requires \usepackage{colortbl} instead of \usepackage[table,xcdraw]{xcolor}
\begin{table}[]
\begin{tabular}{
>{\columncolor[HTML]{2f414a}}c 
>{\columncolor[HTML]{2f414a}}c 
>{\columncolor[HTML]{2f414a}}c 
>{\columncolor[HTML]{2f414a}}c l}
\cellcolor[HTML]{1f5059}\textbf{종류} & \cellcolor[HTML]{1f5059}\textbf{기호} & \cellcolor[HTML]{1f5059}\textbf{설명}                                                                                                  & \cellcolor[HTML]{1f5059}\textbf{단축 평가 여부}                 &  \\
조건부 AND                             & \&\&                                & \begin{tabular}[c]{@{}c@{}}두   개의 피연산자가 모두 TRUE일 때만 TRUE로 반환,\\      한 쪽이라도 FALSE면 FALSE로 반환\end{tabular}                            & 왼쪽   피연산자 먼저 평가 -\textgreater 값이 FALSE 이면 우측 피연산자는 평가 건너뜀 &  \\
비조건부 AND                            & \&                                  & \begin{tabular}[c]{@{}c@{}}두   개의 피연산자가 모두 TRUE일 때만 TRUE로 반환,\\      한 쪽이라도 FALSE면 FALSE로 반환\end{tabular}                            & X                                                         &  \\
조건부 OR                              & \textbackslash{}|\textbackslash{}|  & \begin{tabular}[c]{@{}c@{}}두   개의 피연산자 중 하나가 TRUE면 TRUE로 반환,\\      두 피연산자 모두 FALSE면 FALSE로 반환\end{tabular}                          & 왼쪽   피연산자 먼저 평가 -\textgreater 값이 TRUE 이면 우측 피연산자는 평가 건너뜀  &  \\
비조건부 OR                             & \textbackslash{}|                   & \begin{tabular}[c]{@{}c@{}}두   개의 피연산자 중 하나가 TRUE면 TRUE로 반환,\\      두 피연산자 모두 FALSE면 FALSE로 반환\end{tabular}                          & X                                                         &  \\
배타적 논리합 XOR                         & \textbackslash{}\textasciicircum{}  & \begin{tabular}[c]{@{}c@{}}두   개의 피연산자의 값이 서로 다를 경우에만 TRUE로 반환,\\      두피연산자의 값이 서로 같을 경우 FALSE로 반환\end{tabular}                     & X                                                         &  \\
논리 부정 NOT                           & \textbackslash{}!                   & \begin{tabular}[c]{@{}c@{}}단항   연산자로, 피연산자의 논리 값을 반대로 뒤집음,\\      !TRUE -\textgreater FALSE / !FALSE -\textgreater TRUE\end{tabular} & X                                                         & 
\end{tabular}
\end{table}