---
title: "IDebugEntryPointEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEntryPointEvent2"
helpviewer_keywords: 
  - "IDebugEntryPointEvent2 인터페이스"
ms.assetid: a15d1cc3-97b7-438c-8d24-c23149708f42
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugEntryPointEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\) 프로그램 첫 번째 명령 사용자 코드를 실행 하려고 할 때이 인터페이스 세션 디버그 매니저 \(SDM\)을 보냅니다.  
  
## 구문  
  
```  
IDebugEntryPointEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE의 정상적인 작업의 일부로 서이 인터페이스를 구현합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 DE를 만들고 디버깅 중인 프로그램에 로드 되 고 첫 번째 명령 사용자 코드를 실행할 준비가 되 면이 이벤트 개체를 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 되는 콜백 함수입니다.  
  
## 설명  
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)프로그램의 첫 번째 명령을 실행 하려고 할 때 전송 됩니다.  예를 들어, `IDebugEntryPoint2` 프로그램은 사용자가 실행 하려고 할 때 전송 됩니다 `main` 함수입니다.  
  
 시기는 DE을 보냅니다 `IDebugEntryPointEvent2`, 현재 코드 위치 사용자 코드에 있는 첫 번째 명령이 마찬가지로 해야 `main`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)