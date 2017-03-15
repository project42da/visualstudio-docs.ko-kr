---
title: "marker_series::write_alert 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvmarkersobj/Concurrency::diagnostic:marker_series::write_alert"
helpviewer_keywords: 
  - "Concurrency::diagnostic:marker_series::write_alert 메서드"
ms.assetid: 9d5465c7-f862-47a7-b249-4116605075a6
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# marker_series::write_alert 메서드
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

동시성 시각화 추적 파일에 경고를 씁니다.  
  
## 구문  
  
```  
void write_alert(  
   _In_ LPCTSTR _Format,  
   ...  
);  
```  
  
#### 매개 변수  
 `_Format`  
 인수 목록에서 배열의 개체에 해당하는 0개 이상의 서식 항목과 혼합된 텍스트를 포함하는 복합컨트롤 문자열입니다.  
  
## 요구 사항  
 **헤더:** cvmarkersobj.h  
  
 **네임스페이스:** Concurrency::diagnostic  
  
## 참고 항목  
 [marker\_series 클래스](../profiling/marker-series-class.md)