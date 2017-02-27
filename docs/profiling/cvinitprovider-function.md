---
title: "CvInitProvider 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvmarkers/CvInitProvider"
helpviewer_keywords: 
  - "CvInitProvider 메서드"
ms.assetid: ba1863ad-e35f-4d34-a2f2-5e68957d1915
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# CvInitProvider 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

표시기 공급자를 초기화합니다.  다른 동시성 시각화 도우미 SDK 함수 보다 먼저 호출 되어야 합니다.  
  
## 구문  
  
```  
HRESULT CvInitProvider(  
   _In_ const GUID* pGuid,  
   _Out_ PCV_PROVIDER* ppProvider  
);  
```  
  
#### 매개 변수  
 `pGuid`  
 공급자의 guid입니다.  NULL 일 수 없습니다.  
  
 `ppProvider`  
 공급자 컨텍스트를 저장할 출력 변수의 주소입니다.  NULL 일 수 없습니다.  
  
## 반환 값  
 공급자가 성공적으로 초기화 되거나 모든 오류가 있을 경우 오류 코드 S\_OK입니다.  성공\/실패 매크로를 사용하여 오류 조건을 확인할 수 있습니다.  
  
## 요구 사항  
 **헤더:** cvmarkers.h  
  
## 참고 항목  
 [C\+\+ 라이브러리 참조](../profiling/cpp-library-reference.md)