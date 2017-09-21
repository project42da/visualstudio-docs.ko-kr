---
title: "IDebugProgram2::EnumModules | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgram2::EnumModules"
helpviewer_keywords: 
  - "IDebugProgram2::EnumModules"
ms.assetid: 876ac9da-3b7c-4156-b79a-8f340e9fcea6
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProgram2::EnumModules
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 프로그램이 로드 되 고 실행 되는 모듈의 목록을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumModules(   
   IEnumDebugModules2** ppEnum  
);  
```  
  
```c#  
int EnumModules(   
   out IEnumDebugModules2 ppEnum  
);  
```  
  
#### 매개 변수  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md) 모듈의 목록을 포함 하는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 모듈은 DLL 또는 어셈블리 이며 일반적으로 표시 되는  **모듈** 디버그 창입니다.  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)