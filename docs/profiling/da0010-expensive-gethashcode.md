---
title: "DA0010: GetHashCode의 부담이 큽니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.rules.DAExpensiveGetHashCode"
  - "vs.performance.DA0010"
  - "vs.performance.rules.DA0010"
  - "vs.performance.10"
ms.assetid: 3987e21a-5b4f-45e4-8a33-6b3f0a472c08
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# DA0010: GetHashCode의 부담이 큽니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0010|  
|범주|.NET Framework 사용|  
|프로파일링 방법|샘플링<br /><br /> .NET 메모리|  
|메시지|GetHashCode 함수는 부담이 적고 메모리를 할당하지 않아야 합니다.  가능한 경우 해시 코드 함수의 복잡성을 줄이십시오.|  
|메시지 형식|경고|  
  
## 원인  
 해당 형식의 GetHashCode 메서드에 대한 호출이 프로파일링 데이터의 상당 비율을 차지하거나 이 메서드가 메모리를 할당합니다.  
  
## 규칙 설명  
 해시는 크기가 큰 컬렉션에서 특정 항목을 빠르게 찾는 기술입니다.  해시 테이블은 크기가 매우 클 수 있고 많은 액세스를 지원해야 하기 때문에 매우 효율적이어야 합니다.  이 요구 사항에 따라 .NET Framework의 GetHashCode 메서드는 메모리를 할당하지 않아야 합니다.  메모리를 할당하면 가비지 수집기의 로드가 증가하고 할당 요청의 결과로 가비지 수집을 실행해야 하는 경우 메서드가 지연될 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 메서드의 복잡성을 줄입니다.