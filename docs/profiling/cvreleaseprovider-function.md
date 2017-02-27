---
title: "CvReleaseProvider 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvmarkers/CvReleaseProvider"
helpviewer_keywords: 
  - "CvReleaseProvider 메서드"
ms.assetid: 8d74379e-295d-452b-bd5f-0769df387d4f
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# CvReleaseProvider 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

릴리스 표시기 공급자입니다.  표시기 공급자를 해제 이전에 만든된 마커 일련의이 공급자는 변경 되지 않습니다.  표식이 계열 CvReleaseMarkerSeries 호출에 의해 개별적으로 분리 해야 합니다.  공급자를 해제 하지 않으면 메모리 누수가 발생 합니다.  
  
## 구문  
  
```  
HRESULT CvReleaseProvider(  
   _In_ PCV_PROVIDER pProvider  
);  
```  
  
#### 매개 변수  
 `pProvider`  
 공급자 컨텍스트가 있습니다.  NULL 일 수 없습니다.  
  
## 반환 값  
 공급자가 성공적으로 초기화 되거나 모든 오류가 있을 경우 오류 코드 S\_OK입니다.  성공\/실패 매크로를 사용하여 오류 조건을 확인할 수 있습니다.  
  
## 요구 사항  
 **헤더:** cvmarkers.h  
  
## 참고 항목  
 [C\+\+ 라이브러리 참조](../profiling/cpp-library-reference.md)