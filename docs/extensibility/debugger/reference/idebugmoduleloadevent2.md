---
title: "IDebugModuleLoadEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugModuleLoadEvent2"
helpviewer_keywords: 
  - "IDebugModuleLoadEvent2 인터페이스"
ms.assetid: 7d26fb23-5d49-4ba7-b7c5-3aed4d7be81e
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugModuleLoadEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 엔진 \(DE\) 모듈이 로드 되거나 언로드될 때 세션 디버그 매니저 \(SDM\) 보내집니다.  
  
## 구문  
  
```  
IDebugModuleLoadEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE 모듈의 로드 또는 언로드 했습니다 보고서에이 인터페이스를 구현 합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 DE를 만들고 모듈을 로드 하거나 언로드한 보고서에이 이벤트 개체를 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 되 면 SDM가 제공 되는 콜백 함수입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugModuleLoadEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetModule](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md)|되는 모듈을 가져옵니다 로드 또는 언로드.|  
  
## 설명  
 Visual Studio이 이벤트를 사용 하 여 유지는  **모듈** 최신 창입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)