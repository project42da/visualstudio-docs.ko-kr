---
title: "IDebugPortEx2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortEx2"
helpviewer_keywords: 
  - "IDebugPortEx2 인터페이스"
ms.assetid: 144724d0-38ee-4c9b-87ca-8a504371182b
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IDebugPortEx2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 세션을 매니저 \(SDM\) 컨트롤 프로그램 및 포트에서 실행 되는 프로세스를 디버깅할 수 있습니다.  
  
## 구문  
  
```  
IDebugPortEx2 : IUnknown  
```  
  
## 구현자 참고 사항  
 사용자 지정 포트 공급자를 구현 하는 동일한 개체에서이 인터페이스를 구현 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md).  
  
## 호출자에 대 한 참고 사항  
 SDM 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 `IDebugPort2` 이 인터페이스를 가져올 수 있는 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugPortEx2`.  
  
|메서드|설명|  
|---------|--------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)|실행 파일을 시작합니다.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)|프로세스의 실행을 다시 시작 합니다.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugportex2-canterminateprocess.md)|프로세스를 종료할 수 있는지 여부를 결정 합니다.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugportex2-terminateprocess.md)|프로세스를 종료합니다.|  
|[GetPortProcessId](../../../extensibility/debugger/reference/idebugportex2-getportprocessid.md)|포트 자체의 프로세스 ID를 가져옵니다.|  
|[GetProgram](../../../extensibility/debugger/reference/idebugportex2-getprogram.md)|프로그램 노드와 연결 된 프로그램을 가져옵니다.|  
  
## 설명  
 이 인터페이스는 SDM에서 사용자 지정 포트 공급자 사이의 일반적으로 개인입니다.  
  
 원하는 경우 디버그 엔진 \(DE\)이이 인터페이스를 찾을 수 있습니다 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 인터페이스를 전달 합니다 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) 사용 하 고 [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) 프로그램을 시작 합니다.  그러나이 것입니다 하는 DE 요청 프로그램을 실행 하는 데 필요한 모든 것을 수행할 수 있습니다.  
  
## 요구 사항  
 헤더: portpriv.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)