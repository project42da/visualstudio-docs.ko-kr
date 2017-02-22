---
title: "IDebugPortSupplier2::AddPort | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortSupplier2::AddPort"
helpviewer_keywords: 
  - "IDebugPortSupplier2::AddPort"
ms.assetid: df491161-6bf3-4fcc-b478-b9ec88ec995f
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugPortSupplier2::AddPort
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트를 추가합니다.  
  
## 구문  
  
```cpp#  
HRESULT AddPort(   
   IDebugPortRequest2* pRequest,  
   IDebugPort2**       ppPort  
);  
```  
  
```c#  
int AddPort(   
   IDebugPortRequest2 pRequest,  
   out IDebugPort2    ppPort  
);  
```  
  
#### 매개 변수  
 `pRequest`  
 \[in\] [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) 추가할 포트를 설명 하는 개체입니다.  
  
 `ppPort`  
 \[out\] 반환 된 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 포트를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 실제로 활성 포트로 포트 공급자 내부 목록에 추가 하는 것 뿐만 아니라 요청한 포트를 만듭니다.  [CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md) 메서드를 호출 먼저 가능한 시간이 지연 되지 않도록 합니다.  
  
## 참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)