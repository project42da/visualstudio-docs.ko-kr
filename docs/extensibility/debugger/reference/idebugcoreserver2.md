---
title: "IDebugCoreServer2 | Microsoft Docs"
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
  - "IDebugCoreServer2"
helpviewer_keywords: 
  - "IDebugCoreServer2 인터페이스"
ms.assetid: 9c47d0a6-9eb1-464e-bd44-fa2b552d4d36
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugCoreServer2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스를 사용 하 여 표현 하 고 서버는 네트워크 상의 컴퓨터에서 정보를 얻을 합니다.  
  
## 구문  
  
```  
IDebugCoreServer2 : IUknown  
```  
  
## 구현자 참고 사항  
 Visual Studio 서버를 나타내는 데이 인터페이스를 구현 합니다.  Visual Studio 각 인스턴스에이 인터페이스의 인스턴스를 만듭니다.  
  
## 호출자에 대 한 참고 사항  
 호출 하는 데이 인터페이스를 수신 하는 포트 사용자 지정 협력 업체 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md).  
  
 디버그 엔진은이 인터페이스에 대 한 호출을 통해 간접적으로 얻을 수 있습니다 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md) \(어떤 반환 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)에서 파생 된 인터페이스 `IDebugCoreServer2`\).  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugCoreServer2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)|이름 및 컴퓨터의 특성을 가져옵니다.|  
|[GetMachineName](../../../extensibility/debugger/reference/idebugcoreserver2-getmachinename.md)|컴퓨터의 이름을 가져옵니다.|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)|컴퓨터에 존재 하는 포트 공급자를 가져옵니다.|  
|[GetPort](../../../extensibility/debugger/reference/idebugcoreserver2-getport.md)|이미 컴퓨터에 있는 포트를 가져옵니다.|  
|[EnumPorts](../../../extensibility/debugger/reference/idebugcoreserver2-enumports.md)|컴퓨터에서 모든 포트에 대 한 열거자를 만듭니다.|  
|[EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)|컴퓨터에서 모든 포트 공급자에 대 한 열거자를 만듭니다.|  
|[GetMachineUtilities\_V7](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineutilities-v7.md)|시스템 유틸리티를 대 한 컴퓨터를 가져옵니다.|  
  
## 설명  
 이 인터페이스 네트워크에 있는 컴퓨터에서 실행 중인 프로세스를 검색 하 여 Visual Studio 사용 됩니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)   
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)