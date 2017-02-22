---
title: "DA0011: CompareTo의 부담이 큽니다. | Microsoft Docs"
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
  - "vs.performance.DA0011"
  - "vs.performance.rules.DAExpensiveCompareTo"
  - "vs.performance.11"
  - "vs.performance.rules.DA0011"
ms.assetid: 239a381d-0d97-4367-8668-746c93f5af2c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DA0011: CompareTo의 부담이 큽니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0011|  
|범주|.NET Framework 사용|  
|프로파일링 방법|샘플링<br /><br /> .NET 메모리|  
|메시지|CompareTo 함수는 부담이 적고 메모리를 할당하지 않아야 합니다.  가능한 경우 compareTo 함수의 복잡성을 줄이십시오.|  
|규칙 유형|경고|  
  
## 원인  
 형식의 CompareTo 메서드가 부담이 크거나 메모리를 할당합니다.  
  
## 규칙 설명  
 CompareTo 메서드는 효율적이어야 하며 메모리를 할당하지 않아야 합니다.  
  
## 위반 문제를 해결하는 방법  
 CompareTo 메서드의 복잡성을 줄입니다.