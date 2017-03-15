---
title: "BP_LOCATION_CODE_FUNC_OFFSET | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_LOCATION_CODE_FUNC_OFFSET"
helpviewer_keywords: 
  - "BP_LOCATION_CODE_FUNC_OFFSET 구조"
ms.assetid: ab38f7ca-fa01-4cf3-a06c-56cbb7207617
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# BP_LOCATION_CODE_FUNC_OFFSET
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

코드에서 함수에서 중단점의 오프셋된 위치를 설명합니다.  
  
## 구문  
  
```cpp#  
typedef struct _BP_LOCATION_CODE_FUNC_OFFSET {   
   BSTR                     bstrContext;  
   IDebugFunctionPosition2* pFuncPos;  
} BP_LOCATION_CODE_FUNC_OFFSET;  
```  
  
## Members  
 `bstrContext`  
 중단점의, 일반적으로 호출 스택에 표시 되는 메서드 또는 함수의 이름입니다.  
  
 `pFuncPos`  
 [IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md) 함수 이름과 함수의 시작 부분에서 상대 위치를 설명 하는 개체입니다.  
  
## 설명  
 이 구조체의 멤버인는 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 구조체 합집합 일부로.  
  
 `pFuncPos` 멤버 함수 중단점을 설정할 수 있는 위치를 나타냅니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)