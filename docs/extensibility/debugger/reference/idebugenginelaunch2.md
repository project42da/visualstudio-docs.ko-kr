---
title: "IDebugEngineLaunch2 | Microsoft Docs"
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
  - "IDebugEngineLaunch2"
helpviewer_keywords: 
  - "IDebugEngineLaunch2 인터페이스"
ms.assetid: 5eaf2ad8-3fbf-446e-b48b-5327ad3f5255
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugEngineLaunch2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\)에서 시작 하 고 프로그램을 종료 하는 데 사용.  
  
## 구문  
  
```  
IDebugEngineLaunch2 : IDebugEngine2  
```  
  
## 구현자 참고 사항  
 사용자 지정 포트에서 완전히 처리할 수 없는 프로세스가 실행 하는 데 특별 한 요구 사항이 있는 경우이 인터페이스는 사용자 지정 DE에서 구현 됩니다.  이러한 일반적으로 DE는 인터프리터의 일부인 경우 스크립트 디버깅 되는 프로세스입니다 경우: 인터프리터 먼저 시작 하 고 스크립트를 로드 하 고 시작 및 다음.  포트 인터프리터를 시작할 수 있지만 스크립트는 역할은 DE 있는 특수 한 처리를 해야 할 수 있습니다.  이 인터페이스는 고유한 요구 사항에 대해 사용자 지정 포트를 처리할 수 없습니다 프로그램 실행 경우에 구현 됩니다.  
  
## 호출자에 대 한 참고 사항  
 SDM은이 인터페이스를 가져올 수 있습니다 경우이 인터페이스 세션 디버그 매니저 \(SDM\)에서 호출 되는 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 인터페이스 \(Queryinterface를 사용\).  이 인터페이스를 얻을 수 있는 경우는 DE 특별 한 요구 사항이 있고이 유틸리티를 실행 하는 포트 대신 프로그램을 실행 하기 위해이 인터페이스를 호출 하는 SDM 알 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugEngineLaunch2`.  
  
|메서드|설명|  
|---------|--------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)|DE 방법으로 프로세스를 시작 합니다.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)|다시 실행을 처리합니다.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-canterminateprocess.md)|프로세스를 종료 하는 경우를 결정 합니다.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)|프로세스를 종료합니다.|  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)