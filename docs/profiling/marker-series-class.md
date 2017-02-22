---
title: "marker_series 클래스 | Microsoft Docs"
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
  - "cvmarkersobj/Concurrency::diagnostic::marker_series"
helpviewer_keywords: 
  - "Concurrency::diagnostic::marker_series 클래스"
ms.assetid: b8445ed0-c512-4f92-b6b4-3d05c044f939
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# marker_series 클래스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

단일 공급자가 생성한 이벤트의 직렬 채널을 나타냅니다.  
  
## 구문  
  
```  
class marker_series;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[marker\_series::marker\_series 생성자](../Topic/marker_series::marker_series%20Constructor.md)|`marker_series` 클래스의 새 인스턴스를 초기화합니다.|  
|[marker\_series::~marker\_series 소멸자](../profiling/marker-series-tilde-marker-series-destructor.md)|Marker\_series 개체를 삭제하고 할당된 모든 리소스를 해제 합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[marker\_series::is\_enabled 메서드](../Topic/marker_series::is_enabled%20Method.md)|어떤 세션이 공급자에게 가능하도록 제공하는 것을 결정합니다.|  
|[marker\_series::write\_alert 메서드](../profiling/marker-series-write-alert-method.md)|동시성 시각화 추적 파일에 경고를 씁니다.|  
|[marker\_series::write\_flag 메서드](../profiling/marker-series-write-flag-method.md)|동시성 시각화 추적 파일에 플래그를 씁니다.|  
|[marker\_series::write\_message 메서드](../profiling/marker-series-write-message-method.md)|동시성 시각화 추적 파일에 메시지를 씁니다.|  
  
## 상속 계층  
 `marker_series`  
  
## 요구 사항  
 **헤더:** cvmarkersobj.h  
  
 **네임스페이스:** Concurrency::diagnostic  
  
## 참고 항목  
 [진단 네임스페이스](../profiling/diagnostic-namespace.md)