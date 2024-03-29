---
title: "[Algorithm] 시간복잡도"
layout: post
date: 2019-10-28 22:48
image: /assets/images/markdown.jpg
headerImage: false
tag:
- algorithm
category: blog
author: kyudongPark
description: 알고리즘의 시간복잡도에 대하여
---

이번 글에서는 알고리즘의 시간복잡도에 대해 알아보겠습니다.

시간복잡도는 알고리즘이 문제를 해결하기 위한 **'연산의 횟수'** 를 말합니다.  
단순히 이렇게만 보면 무슨 말인지 모르니 천천히 설명해 보도록 하겠습니다.  

먼저 알고리즘이란 무엇일까요? 
* 어떠한 결과를 만들기 위한 과정들
* 다양한 상황에 따라 다름 

즉, CS에서는 어떠한 문제를 해결하기 위한 절차나 방법들을 이야기한다.

예를 들어, 우리가 차를 타고 흑석동에서 청담동으로 이동하려고 합니다. 이 때, 청담동은 결과가 됩니다. 그리고 청담동에 도착할 때까지의 과정들이 알고리즘이 됩니다.  

* 차를 탄다 
* 현재 가는 길에 막히는 곳이 있는지 찾는다
* 막히지 않는 곳을 선택
* . . .
* . . .
* 도착

위와 같은 일련의 과정들을 알고리즘이라고 하는 것입니다! 또한 과정들은 다른 도로를 이용한다던지, 사고가 나서 돌아간다던지 등의 상황들로 변경될 수 있기 때문에 한가지가 아닐 경우가 많습니다!  
흔히, CS에서 어떠한 문제를 해결하기 위해 더 빠른 성능의 방법을 찾는 것이 굉장히 중요합니다.  

그렇다면 더 빠른 성능은 어떻게 판단할 수 있을까요? 알고리즘의 성능은 보통 다음의 2가지로 판단합니다.

* 실행시간 ( 시간복잡도 )
* 메모리 사용량 ( 공간복잡도 )

입니다.  

여기서 실행시간은 컴퓨터가 알고리즘 코드를 실행하는 속도에 의존합니다. 컴퓨터의 처리속도, 사용된 언어, 컴파일러의 속도 등 여러가지에 의존합니다.  
실행시간은 2가지로 나뉘어지는데, 

* 입력값(N)의 크기
* 입력값(N)의 크기에 따른 함수의 증가량 ( 성장률 )

입니다.

하지만 매번 다른 상황에서 판단한다면 정확하게 비교할 수가 없겠죠? 그래서 우리는 **점근적 분석** 을 사용합니다. 
CS에서는 보통 엄청나게 많고 큰 데이터를 사용하기 때문에 각 알고리즘이 주어진 큰 데이터(입력값)의 크기를 기준으로 수행시간이나 사용하는 공간이 얼마인지 객관적으로 비교할 수 있는 기준을 제시해 주는 것이 바로 점근적 분석입니다.     
또한, 2번의 함수의 증가량에서 중요하지 않은 계수들을 제거하게 되면 증가량에 집중할 수 있게 되는데 이를 **점근적 표기법(Asymptotic notation)** 이라고 합니다. 

우리는 3가지 접근적 표기법을 사용합니다. 

* 최선의 경우 ( Best case ) --> Ω 오메가 표기법
* 최악의 경우 ( Worst case ) --> O 빅오 표기법
* 평균의 경우 ( Average case ) --> θ 세타 표기법

오메가 표기법은 점근적 하한선(Asymptotic lower bound) 로 주어진 알고리즘이 아무리 좋아도 비교하는 함수와 같거나 나쁘다. 
이해하기 쉽게 그림으로 표현하면 
![Omega notation](../assets/images/omega.jpeg)

즉, n을 기준으로 n보다 오른쪽에 있는 모든 n(입력값)에 대해 함수 f(n)은 함수 cg(n)보다 크거나 같다는 의미이다. 


세타 표기법은 점근적 상한선과 점근적 하한선의 교집합(Asymptotic tighter bound)으로 주어진 알고리즘이 아무리 좋아지거나 나빠지더라도 비교하는 함수의 범위안에 있다.

이해하기 쉽게 그림으로 표현하면 
![Theta notation](../assets/images/theta.jpeg)

n을 기준으로 n보다 오른쪽에 있는 모든 n(입력값)에 대해 함수 f(n)은 함수 c1g(n)보다 크거가 같고 c2g(n)보다 작거나 같다.


빅오 표기법은 점근적 상한선(Asymptotic upper bound)으로 주어진 알고리즘이 아무리 나빠도 비교하는 함수와 같거나 좋다.

이해하기 쉽게 그림으로 표현하면 
![BigO notation](../assets/images/bigo.jpeg)

n을 기준으로 n보다 오른쪽에 있는 모든 n(입력값)에 대해 함수 f(n)은 함수 cg(n)보다 작거나 같다는 의미이다. 

그래서 실제 수행시간이 아닌 알고리즘의 성능분석을 위해 컴퓨터의 성능을 제외한 **연산의 횟수** 만을 생각하여 판단하게 됩니다.  
이것이 바로 **시간복잡도** 입니다. 즉, 입력값(N)에 따른 연산의 횟수입니다.

보통 평균을 구하는 것은 어렵고 복잡하기 때문에 우리는 최악의 경우인 Big - O 표기법을 주로 사용합니다.  























