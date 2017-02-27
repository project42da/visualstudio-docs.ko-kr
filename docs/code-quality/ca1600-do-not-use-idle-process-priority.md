---
title: "CA1600: 유휴 상태 프로세스 우선 순위를 사용하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DoNotUseIdleProcessPriority"
  - "CA1600"
helpviewer_keywords: 
  - "CA1600"
  - "DoNotUseIdleProcessPriority"
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 15
---
# CA1600: 유휴 상태 프로세스 우선 순위를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotUseIdleProcessPriority|  
|CheckId|CA1600|  
|범주|Microsoft.Mobility|  
|변경 수준|주요 변경|  
  
## 원인  
 프로세스가 `ProcessPriorityClass.Idle`로 설정되면 이 규칙이 적용됩니다.  
  
## 규칙 설명  
 프로세스 우선 순위를 유휴 상태로 설정하지 마십시오.  `System.Diagnostics.ProcessPriorityClass.Idle`인 프로세스는 어떠한 이유로든 유휴 상태가 될 경우 CPU를 차지하므로 블록이 대기 모드가 됩니다.  
  
## 위반 문제를 해결하는 방법  
 프로세스를 `ProcessPriorityClass.BelowNormal`로 설정합니다.  
  
## 경고를 표시하지 않는 경우  
 유휴 상태 프로세스 우선 순위가 필요하고 이동성 고려 사항을 무시해도 안전한 경우에만 이 규칙을 표시하지 않습니다.