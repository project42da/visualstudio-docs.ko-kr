---
title: "marker_series::write_flag 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvmarkersojb/Concurrency::diagnostic::marker_series::write_flag"
helpviewer_keywords: 
  - "Concurrency::diagnostic::marker_series::write_flag 메서드"
ms.assetid: ca07f388-e5d5-46fd-b991-fe6e9029a68f
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# marker_series::write_flag 메서드
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

동시성 시각화 추적 파일에 플래그를 씁니다.  
  
## 구문  
  
```  
void write_flag(  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_flag(  
   marker_importance _Importance,  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_flag(  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_flag(  
   marker_importance _Importance,  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
```  
  
#### 매개 변수  
 `_Format`  
 인수 목록에서 배열의 개체에 해당하는 0개 이상의 서식 항목과 혼합된 텍스트를 포함하는 복합컨트롤 문자열입니다.  
  
 `_Importance`  
 중요도 수준입니다.  
  
 `_Category`  
 카테고리입니다.  
  
## 요구 사항  
 **헤더:** cvmarkersobj.h  
  
 **네임스페이스:** Concurrency::diagnostic  
  
## 참고 항목  
 [marker\_series 클래스](../profiling/marker-series-class.md)