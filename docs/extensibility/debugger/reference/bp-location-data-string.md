---
title: "BP_LOCATION_DATA_STRING | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_LOCATION_DATA_STRING"
helpviewer_keywords: 
  - "BP_LOCATION_DATA_STRING 구조"
ms.assetid: 445d6f3f-95b0-47ac-85e2-51b778240687
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# BP_LOCATION_DATA_STRING
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

통합된 개발 환경 \(IDE\)에서 사용자가 입력할 수 있는 문자열을 기반으로 하는 데이터 중단점을 설정 하는 데 사용 됩니다.  
  
## 구문  
  
```cpp#  
typedef struct _BP_LOCATION_DATA_STRING {   
   IDebugThread2* pThread;  
   BSTR           bstrContext;  
   BSTR           bstrDataExpr;  
   DWORD          dwNumElements;  
} BP_LOCATION_DATA_STRING;  
```  
  
## Members  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 에 중단점이 발생 하는 스레드를 나타내는 개체입니다.  
  
 `bstrContext`  
 코드에서 중단점을, 일반적으로 메서드 또는 함수 이름은 호출 스택에 표시 되는 컨텍스트.  
  
 `bstrDataExpr`  
 데이터 문자열에 중단점을 설정 하는 사용자를 입력 합니다.  
  
 `dwNumElements`  
 중단점이 발생 데이터 문자열에서 요소의 수입니다.  
  
## 설명  
 이 구조체의 멤버인는 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 구조체 합집합 일부로.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)