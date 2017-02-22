---
title: "CA1601: 전원 상태 변경을 방해하는 타이머를 사용하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1601"
  - "DoNotUseTimersThatPreventPowerStateChanges"
helpviewer_keywords: 
  - "CA1601"
  - "DoNotUseTimersThatPreventPowerStateChanges"
ms.assetid: b8028c92-0696-4c54-9773-0028f29bda9a
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1601: 전원 상태 변경을 방해하는 타이머를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotUseTimersThatPreventPowerStateChanges|  
|CheckId|CA1601|  
|범주|Microsoft.Mobility|  
|변경 수준|주요 변경|  
  
## 원인  
 타이머가 1초에 두 번 이상 발생하도록 간격이 설정되어 있습니다.  
  
## 규칙 설명  
 1초에 두 번 이상 폴링하거나 1초에 두 번 이상 발생하는 타이머는 사용하지 않는 것이 좋습니다.  정기적인 작업의 실행 빈도가 높아지면 CPU 사용률도 높아져 디스플레이 및 하드 디스크를 끄는 절전 유휴 타이머에 방해가 됩니다.  
  
## 위반 문제를 해결하는 방법  
 타이머 간격을 1초에 한 번 미만 발생하도록 설정합니다.  
  
## 경고를 표시하지 않는 경우  
 타이머를 1초에 두 번 이상 발생시켜야 하고 이동성 고려 사항을 무시해도 안전한 경우에만 이 규칙을 표시하지 않습니다.