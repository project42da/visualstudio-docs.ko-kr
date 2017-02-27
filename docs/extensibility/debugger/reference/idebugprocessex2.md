---
title: "IDebugProcessEx2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProcessEx2"
helpviewer_keywords: 
  - "IDebugProcessEx2 인터페이스"
ms.assetid: 44e309ba-1d6f-499b-aa7e-9b34858a6d57
caps.latest.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 21
---
# IDebugProcessEx2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 세션을 디버그 매니저 \(SDM\)를 연결 하거나 프로세스에서 분리 해도 프로세스를 알릴 수 있습니다.  
  
## 구문  
  
```  
IDebugProcessEx2 : IUnknown  
```  
  
## 구현자 참고 사항  
 동일한 개체에서이 인터페이스를 구현 하는 사용자 지정 포트 공급자는 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 인터페이스를.  
  
-   프로세스에 연결 된 세션의 추적을 지원  
  
-   여러 디버깅 엔진에서 지원 자동\-연결  
  
 사용자 지정 포트 공급자는 선택한 경우이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
  
-   SDM 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 `IDebugProcess2` 이 인터페이스를 가져올 수 있는 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugProcessEx2`.  
  
|메서드|설명|  
|---------|--------|  
|[연결](../../../extensibility/debugger/reference/idebugprocessex2-attach.md)|세션 프로세스는 현재 디버깅 하는 프로세스 알려 줍니다.|  
|[Detach](../../../extensibility/debugger/reference/idebugprocessex2-detach.md)|세션 프로세스 더 이상 디버깅 되는 프로세스 알려 줍니다.|  
|[AddImplicitProgramNodes](../../../extensibility/debugger/reference/idebugprocessex2-addimplicitprogramnodes.md)|디버깅 엔진의 목록에 대 한 프로그램이 노드를 추가 하는 예제입니다.|  
  
## 설명  
 이 인터페이스는 SDM 및 프로세스 간에 개인입니다.  
  
## 요구 사항  
 헤더: Portpriv.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)