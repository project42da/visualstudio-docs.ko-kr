---
title: "IDebugProcessSecurity | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugProcessSecurity 인터페이스"
ms.assetid: 8a52ddca-bd99-49c0-9778-469dce7abd44
caps.latest.revision: 4
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 4
---
# IDebugProcessSecurity
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

`IDebugProcessSecurity`사용자가 프로세스에 연결 안전 하지 않다고 경고할 포트 업체로 구현 됩니다.  
  
## 구문  
  
```  
IDebugProcessSecurity : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugProcessSecurity`.  
  
|메서드|설명|  
|---------|--------|  
|[GetUserName](../../../extensibility/debugger/reference/idebugprocesssecurity-getusername.md)|사용자 이름을 포트 공급자에서 가져옵니다.|  
|[QueryCanSafelyAttach](../../../extensibility/debugger/reference/idebugprocesssecurity-querycansafelyattach.md)|사용자가 연결 하 여 디버깅 프로세스에 안전 하지 경고 메시지가 나타납니다.|  
  
## 설명  
 경고를 표시 하 고 사용자가 연결 하려는 프로세스 안전 하지 않다고 간주 수 있습니다 취소할 수이 인터페이스를 구현 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [포트](../../../extensibility/debugger/ports.md)   
 [포트 공급자](../../../extensibility/debugger/port-suppliers.md)   
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)