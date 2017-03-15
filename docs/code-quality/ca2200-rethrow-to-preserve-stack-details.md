---
title: "CA2200: 스택 정보를 유지하도록 다시 throw하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RethrowToPreserveStackDetails"
  - "CA2200"
helpviewer_keywords: 
  - "CA2200"
  - "RethrowToPreserveStackDetails"
ms.assetid: 046e1b98-c4dc-4515-874f-9c0de2285621
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 13
---
# CA2200: 스택 정보를 유지하도록 다시 throw하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|RethrowToPreserveStackDetails|  
|CheckId|CA2200|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 예외가 다시 throw되며 예외가 `throw` 문에 명시적으로 지정되어 있습니다.  
  
## 규칙 설명  
 예외가 throw된 경우 예외가 제공하는 정보에는 스택 추적 정보가 포함되어 있습니다.  스택 추적은 예외를 throw한 메서드로 시작되어 예외를 catch한 메서드로 끝나는 메서드 호출 계층 구조 목록입니다.  `throw` 문에 예외를 지정하여 예외가 다시 throw되면 현재 메서드에서 스택 추적이 다시 시작되고 예외를 throw한 원래 메서드와 현재 메서드 간의 메서드 호출 목록이 손실됩니다.  원래의 스택 추적 정보를 예외와 함께 유지하려면 예외를 지정하지 않고 `throw` 문을 사용합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 예외를 명시적으로 지정하지 않고 예외를 다시 throw합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 `CatchAndRethrowExplicitly` 메서드와 규칙을 충족하는 `CatchAndRethrowImplicitly` 메서드를 보여 줍니다.  
  
 [!code-cs[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/CSharp/ca2200-rethrow-to-preserve-stack-details_1.cs)]
 [!code-vb[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/VisualBasic/ca2200-rethrow-to-preserve-stack-details_1.vb)]