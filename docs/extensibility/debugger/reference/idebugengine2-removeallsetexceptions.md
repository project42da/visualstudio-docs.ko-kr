---
title: "IDebugEngine2::RemoveAllSetExceptions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngine2::RemoveAllSetExceptions"
helpviewer_keywords: 
  - "IDebugEngine2::RemoveAllSetExceptions"
ms.assetid: 165fbe89-802d-4d99-85ca-c10fd6cccc09
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugEngine2::RemoveAllSetExceptions
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

IDE에서 특정 런타임 아키텍처 또는 언어를 설정 하는 예외를 제거 합니다.  
  
## 구문  
  
```cpp#  
HRESULT RemoveAllSetExceptions(   
   REFGUID guidType  
);  
```  
  
```c#  
int RemoveAllSetExceptions(   
   ref Guid guidType  
);  
```  
  
#### 매개 변수  
 `guidType`  
 \[in\] 언어에 대 한 GUID 또는 런타임 아키텍처와 관련 되는 디버그 엔진에 대 한 GUID입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 방법으로 제거 하는 예외에 대 한 이전 호출에 설정 된는 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) 메서드가 있습니다.  
  
 특정 예외를 제거 하려면 호출을 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) 메서드.  
  
## 참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)