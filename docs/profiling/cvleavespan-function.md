---
title: "CvLeaveSpan 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvmarkers/CvLeaveSpan"
helpviewer_keywords: 
  - "CvLeaveSpan 메서드"
ms.assetid: 3bf65fdf-a471-4efd-ac7a-03e701bbae5d
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# CvLeaveSpan 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

범위의 끝을 표시합니다.  
  
## 구문  
  
```  
HRESULT CvLeaveSpan(  
   _In_ PCV_SPAN pSpan  
);  
```  
  
#### 매개 변수  
 `pSpan`  
 CvEnterSpan \*에 대 한 이전 호출에서 반환 된 범위 개체입니다.  NULL 일 수 없습니다.  
  
## 반환 값  
 메시지가 성공적으로 기록 되면 S\_OK입니다.  오류가 있는 경우의 오류 코드입니다.  성공\/실패 매크로를 사용하여 오류 조건을 확인할 수 있습니다.  
  
## 요구 사항  
 **헤더:** cvmarkers.h  
  
## 참고 항목  
 [C\+\+ 라이브러리 참조](../profiling/cpp-library-reference.md)