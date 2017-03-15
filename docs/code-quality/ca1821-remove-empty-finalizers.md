---
title: "CA1821: 빈 종료자를 제거하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RemoveEmptyFinalizers"
  - "CA1821"
helpviewer_keywords: 
  - "CA1821"
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 13
---
# CA1821: 빈 종료자를 제거하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|RemoveEmptyFinalizers|  
|CheckId|CA1821|  
|범주|Microsoft.Performance|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 형식은 빈 종료자를 구현하거나, 기본 형식 종료자만 호출하거나, 조건부로 내보낸 메서드만 호출합니다.  
  
## 규칙 설명  
 개체 수명을 추적할 때에는 추가로 성능 오버헤드가 발생하므로 가능한 경우 종료자를 사용하지 마십시오.  가비지 수집기에서는 개체를 수집하기 전에 종료자를 실행합니다.  즉, 개체를 수집하려면 두 가지 컬렉션이 필요합니다.  빈 종료자는 아무런 장점 없이 오버헤드만 가중시킵니다.  
  
## 위반 문제를 해결하는 방법  
 빈 종료자를 제거합니다.  디버깅하는 데 종료자가 필요하면 전체 종료자를 `#if DEBUG / #endif` 지시문으로 묶습니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 메시지를 표시해야 합니다.  SuppressFinalize를 호출하지 않으면 성능이 저하되고 다른 이점도 없습니다.  
  
## 예제  
 다음 예제에서는 제거할 빈 종료자, `#if DEBUG / #endif` 지시문으로 묶어야 할 종료자 및 `#if DEBUG / #endif` 지시문을 올바르게 사용하는 종료자를 보여 줍니다.  
  
 [!code-cs[FxCop.Performance.RemoveEmptyFinalizers#1](../code-quality/codesnippet/CSharp/ca1821-remove-empty-finalizers_1.cs)]