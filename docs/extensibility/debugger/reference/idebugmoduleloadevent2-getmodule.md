---
title: "IDebugModuleLoadEvent2::GetModule | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugModuleLoadEvent2::GetModule"
helpviewer_keywords: 
  - "IDebugModuleLoadEvent2::GetModule"
ms.assetid: c86482bb-9ce5-4e63-bbe0-969b50169424
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugModuleLoadEvent2::GetModule
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

되는 모듈을 가져옵니다 로드 또는 언로드.  
  
## 구문  
  
```cpp#  
HRESULT GetModule(   
   IDebugModule2** pModule,  
   BSTR*           pbstrDebugMessage,  
   BOOL*           pbLoad  
);  
```  
  
```c#  
int GetModule(   
   out IDebugModule2 pModule,  
   ref string        pbstrDebugMessage,  
   ref int           pbLoad  
);  
```  
  
#### 매개 변수  
 `pModule`  
 \[out\] 반환 된 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) 를 로드 하거나 언로드하는 모듈을 나타내는 개체입니다.  
  
 `pbstrDebugMessage`  
 \[in, out\] 이 이벤트를 설명 하는 메시지를 반환 합니다.  이 매개 변수는 null 값이 있으면 메시지가 요청 됩니다.  
  
 `pbLoad`  
 \[in, out\] 0이 아닌 \(`TRUE`\) 모듈 로드 및 0 인 경우 \(`FALSE`\) 모듈을 언로드하는 경우.  이 매개 변수는 null 값이 있으면 없음 상태를 요청 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)