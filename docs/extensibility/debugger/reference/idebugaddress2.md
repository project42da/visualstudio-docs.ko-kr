---
title: "IDebugAddress2 | Microsoft Docs"
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
  - "IDebugAddress2"
helpviewer_keywords: 
  - "IDebugAddress2 인터페이스"
ms.assetid: b150e0ed-4ac0-4f8c-9732-4b3e54b9d243
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugAddress2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 개체는 주소를 소유 하는 프로세스의 ID에 액세스를이 인터페이스에 의해 표시 되는.  
  
## 구문  
  
```  
IDebugAddress2 : IDebugAddress  
```  
  
## 구현자 참고 사항  
 기호 공급자를 구현 하는 동일한 개체에서이 인터페이스는 구현에서 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  이 인터페이스에이 주소와 관련 된 개체를 소유 하는 프로세스의 ID에 대 한 액세스를 제공 합니다.  
  
## 호출자에 대 한 참고 사항  
 사용 [QueryInterface](/visual-cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수 있는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  
  
## 메서드에서 vtable 순서  
 상속 된 메서드 외에 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetProcessID](../../../extensibility/debugger/reference/idebugaddress2-getprocessid.md)|이 인터페이스에 의해 표시 되는 개체를 소유 하는 프로세스의 ID를 검색 합니다.|  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)