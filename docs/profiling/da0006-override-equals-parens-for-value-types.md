---
title: "DA0006: 값 형식에 대해 Equals()를 재정의하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.rules.DAOverrideEquals"
  - "vs.performance.6"
  - "vs.performance.DA0006"
  - "vs.performance.rules.DA0006"
ms.assetid: 4d85bdd6-b571-47e0-afd6-ba3764e4eed5
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DA0006: 값 형식에 대해 Equals()를 재정의하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0006|  
|범주|.NET Framework 사용|  
|프로파일링 방법|샘플링|  
|메시지|값 형식에 대해 Equals 및 같음 연산자를 재정의하십시오.|  
|메시지 형식|경고|  
  
## 원인  
 public 값 형식의 Equals 메서드 또는 같음 연산자에 대한 호출이 프로파일링 데이터의 상당 비율을 차지합니다.  보다 효율적인 메서드를 구현하는 것이 좋습니다.  
  
## 규칙 설명  
 값 형식의 경우 Equals의 상속된 구현에서 <xref:System.Reflection> 라이브러리를 사용하며 해당 형식의 모든 필드의 내용을 비교합니다.  Reflection에는 많은 계산이 요구되며 모든 필드의 일치 여부를 비교하는 것이 불필요할 수 있습니다.  사용자가 인스턴스를 비교 또는 정렬할 것으로 예측되거나 인스턴스를 해시 테이블 키로 사용할 것으로 예측되는 경우에는 값 형식에서 Equals를 구현해야 합니다.  프로그래밍 언어에서 연산자 오버로딩을 지원하는 경우 같음 연산자와 같지 않음 연산자의 구현도 제공해야 합니다.  
  
 Equals 및 같음 연산자를 재정의하는 방법에 대한 자세한 내용은 [Guidelines for Implementing Equals and the Equality Operator \(\=\=\)](http://go.microsoft.com/fwlink/?LinkId=177818)을 참조하십시오.  
  
## 경고를 조사하는 방법  
 Equals 및 같음 연산자를 구현하는 예제는 코드 분석 규칙 [CA1815: 값 형식에서 Equals 또는 같음 연산자를 재정의하십시오.](../Topic/CA1815:%20Override%20equals%20and%20operator%20equals%20on%20value%20types.md)를 참조하십시오.