---
title: "IDebugPortSupplier2::CanAddPort | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortSupplier2::CanAddPort"
helpviewer_keywords: 
  - "IDebugPortSupplier2::CanAddPort"
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugPortSupplier2::CanAddPort
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트 공급자 새 포트를 추가 하는 방법을 확인 합니다.  
  
## 구문  
  
```cpp#  
HRESULT CanAddPort(   
   void   
);  
```  
  
```c#  
int CanAddPort();  
```  
  
## 반환 값  
 포트를 추가할 수 있는 경우 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 포트가이 포트 공급자를 추가할 수 있습니다 나타낼 수 있습니다.  
  
## 설명  
 호출 하기 전에이 메서드를 호출 하 여 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 메서드를 추가 하는 시간이 많이 걸리는 작업이 될 수 있습니다 뿐만 아니라 포트 두 번째 방법은 만들어지기 때문입니다.  
  
## 참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)