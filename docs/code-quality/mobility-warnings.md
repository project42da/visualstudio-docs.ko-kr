---
title: "이동성 경고 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.codeanalysis.MobilityRules"
helpviewer_keywords: 
  - "이동성 경고 관리 코드 분석 경고"
  - "이동성 경고"
  - "경고, 이동성"
ms.assetid: 9808054c-593b-4fc3-92cc-1fc45f41569c
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 17
---
# 이동성 경고
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이동성 경고는 효율적인 전원 사용을 지원합니다.  
  
## 단원 내용  
  
|규칙|설명|  
|--------|--------|  
|[CA1600: 유휴 상태 프로세스 우선 순위를 사용하지 마십시오.](../code-quality/ca1600-do-not-use-idle-process-priority.md)|프로세스 우선 순위를 유휴 상태로 설정하지 마십시오.  System.Diagnostics.ProcessPriorityClass.Idle인 프로세스는 어떠한 이유로든 유휴 상태가 될 경우 CPU를 차지하므로 블록이 대기 모드가 됩니다.|  
|[CA1601: 전원 상태 변경을 방해하는 타이머를 사용하지 마십시오.](../code-quality/ca1601-do-not-use-timers-that-prevent-power-state-changes.md)|정기적인 작업의 실행 빈도가 높아지면 CPU 사용률도 높아져 디스플레이 및 하드 디스크를 끄는 절전 유휴 타이머에 방해가 됩니다.|