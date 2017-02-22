---
title: "IDebugDefaultPort2::GetPortNotify | Microsoft Docs"
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
  - "IDebugDefaultPort2::GetPortNotify"
helpviewer_keywords: 
  - "IDebugDefaultPort2::GetPortNotify"
ms.assetid: 3ae715ee-9886-4694-a52b-59bb3b27467a
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDefaultPort2::GetPortNotify
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드를 가져옵니다는 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) 이 포트에 대 한 인터페이스입니다.  
  
## 구문  
  
```cpp  
HRESULT GetPortNotify(  
   IDebugPortNotify2** ppPortNotify  
);  
```  
  
```c#  
int GetPortNotify(  
   out IDebugPortNotify2 ppPortNotify  
);  
```  
  
#### 매개 변수  
 `ppPortNotify`  
 \[out\] [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 일반적으로 `QueryInterface` 개체 구현에서 메서드가 호출의 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 인터페이스를 얻을 수는 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) 인터페이스입니다.  원하는 인터페이스는 다른 개체에서 구현 되는 상황입니다.  이 메서드가 이러한 상황을 숨기고 반환의 `IDebugPortNotify2` 인터페이스에서 적절 한 개체입니다.  
  
## 참고 항목  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)