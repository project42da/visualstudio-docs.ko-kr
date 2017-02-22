---
title: "marker_importance 열거형 | Microsoft Docs"
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
  - "cvmarkersobj/Concurrency::diagnostic::marker_importance"
helpviewer_keywords: 
  - "Concurrency::diagnostic::marker_importance 열거형"
ms.assetid: d5524ea0-0227-4d8e-9122-332291042df5
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# marker_importance 열거형
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

동시성 시각화 표식의 중요도 수준을 나타냅니다.  
  
## 구문  
  
```  
enum marker_importance;  
```  
  
## 멤버  
  
### 값  
  
|Name|설명|  
|----------|--------|  
|`critical_importance`|표식의 중요도를 매우 높음으로 지정합니다.|  
|`high_importance`|표식의 중요도를 높음으로 지정합니다.|  
|`low_importance`|표식의 중요도를 낮음으로 지정합니다.|  
|`normal_importance`|표식의 중요도를 보통으로 지정합니다.|  
  
## 요구 사항  
 **헤더:** cvmarkersobj.h  
  
 **네임스페이스:** Concurrency::diagnostic  
  
## 참고 항목  
 [진단 네임스페이스](../profiling/diagnostic-namespace.md)