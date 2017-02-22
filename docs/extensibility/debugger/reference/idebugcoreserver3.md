---
title: "IDebugCoreServer3 | Microsoft Docs"
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
  - "IDebugCoreServer3"
helpviewer_keywords: 
  - "IDebugCoreServer3 인터페이스"
ms.assetid: 51f5f41b-a5a4-4df0-a703-41f3d1811d7f
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugCoreServer3
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 액세스 프로세스를 실행 하는 서버에 대 한 정보를 제공 합니다.  
  
## 구문  
  
```  
IDebugCoreServer3 : IDebugCoreServer2  
```  
  
## 구현자 참고 사항  
 Visual Studio이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 사용 [QueryInterface](/visual-cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수 있는 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) 인터페이스입니다.  호출을 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md) 또한이 인터페이스를 반환 합니다.  이 인터페이스 \(로컬 또는 원격\) 서버에 있는 프로그램을 시작 합니다 사용자 지정 포트 협력 업체에서 가장 많이 사용 됩니다.  
  
## 메서드에서 Vtable 순서  
 메서드 외에 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetServerName](../../../extensibility/debugger/reference/idebugcoreserver3-getservername.md)|서버 이름을 검색합니다.|  
|[GetServerFriendlyName](../../../extensibility/debugger/reference/idebugcoreserver3-getserverfriendlyname.md)|간단한 버전의 서버 이름 검색|  
|[EnableAutoAttach](../../../extensibility/debugger/reference/idebugcoreserver3-enableautoattach.md)|해당 프로세스를 시작할 때 프로세스에 자동으로 연결 하는 특정 디버깅 엔진에 지시 합니다.|  
|[DiagnoseWebDebuggingError](../../../extensibility/debugger/reference/idebugcoreserver3-diagnosewebdebuggingerror.md)|자동으로 연결할 때 오류가 발생 하는 특정 오류 코드를 검색 합니다.|  
|[CreateInstanceInServer](../../../extensibility/debugger/reference/idebugcoreserver3-createinstanceinserver.md)|디버그 엔진의 인스턴스를 서버에 만듭니다.|  
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugcoreserver3-queryislocal.md)|서버는 호출자와 동일한 컴퓨터에 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)|서버와의 통신에 사용 되는 프로토콜을 나타내는 값을 검색 합니다.|  
|[DisableAutoAttach](../../../extensibility/debugger/reference/idebugcoreserver3-disableautoattach.md)|이 서버에서 인식 하는 모든 디버깅 엔진에 대 한 설정을 자동 연결 하는 모든 사용 하지 않습니다.|  
  
## 설명  
 협력 업체 사용자 지정 포트를 수신의 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) 인터페이스를 호출할 때 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md).  `IDebugCoreServer3` 인터페이스는 해당 인터페이스에서 얻을 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)