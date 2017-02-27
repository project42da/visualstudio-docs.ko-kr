---
title: "BP_LOCATION_CODE_ADDRESS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_LOCATION_CODE_ADDRESS"
helpviewer_keywords: 
  - "BP_LOCATION_CODE_ADDRESS 구조"
ms.assetid: 83c9da8b-19d9-4be5-b225-854543654901
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# BP_LOCATION_CODE_ADDRESS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

주소를 코드에서 중단점의 위치를 설명 합니다.  
  
## 구문  
  
```cpp#  
typedef struct _BP_LOCATION_CODE_ADDRESS {   
   BSTR bstrContext;  
   BSTR bstrModuleUrl;  
   BSTR bstrFunction;  
   BSTR bstrAddress;  
} BP_LOCATION_CODE_ADDRESS;  
```  
  
## Members  
 `bstrContext`  
 중단점의, 일반적으로 호출 스택에 표시 되는 메서드 또는 함수의 이름입니다.  
  
 `bstrModuleUrl`  
 중단점이 포함 된 모듈의 URL입니다.  
  
 `bstrFunction`  
 중단점이 포함 된 함수의 이름입니다.  
  
 `bstrAddress`  
 주소 중단점을 바인딩하는 식 계산기가 구문 분석 되는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 개체입니다.  
  
## 설명  
 이 구조체의 멤버인는 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 구조체 합집합 일부로.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)