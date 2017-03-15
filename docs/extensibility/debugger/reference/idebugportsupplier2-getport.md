---
title: "IDebugPortSupplier2::GetPort | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortSupplier2::GetPort"
helpviewer_keywords: 
  - "IDebugPortSupplier2::GetPort"
ms.assetid: d55d5055-7386-4037-bf22-4c3e434a99ca
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPortSupplier2::GetPort
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트를 포트 공급자를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetPort(   
   REFGUID       guidPort,  
   IDebugPort2** ppPort  
);  
```  
  
```c#  
int GetPort(   
   ref Guid        guidPort,  
   out IDebugPort2 ppPort  
);  
```  
  
#### 매개 변수  
 `guidPort`  
 \[in\] 포트의 전역 고유 식별자 \(GUID\)입니다.  
  
 `ppPort`  
 \[out\] 반환 된 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 포트를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_PORTSUPPLIER_NO_PORT` 없음 포트는 해당된 식별자로 존재 하는 경우.  
  
## 참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)