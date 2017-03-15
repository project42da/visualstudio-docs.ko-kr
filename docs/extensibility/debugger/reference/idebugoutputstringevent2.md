---
title: "IDebugOutputStringEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugOutputStringEvent2"
helpviewer_keywords: 
  - "IDebugOutputStringEvent2 인터페이스"
ms.assetid: 86596fd1-cecc-4813-8add-dc3d70068f9b
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugOutputStringEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 엔진 \(DE\) 세션 디버그 매니저 \(SDM\) 문자열 출력에 전송 됩니다.  
  
## 구문  
  
```  
IDebugOutputStringEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE 보내는 문자열에이 인터페이스를 구현 합니다.는  **출력** ide 창입니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 DE를 만들어이 이벤트 개체는 문자열을 보낼 수를 보내는  **출력** 창입니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 되 면 SDM가 제공 되는 콜백 함수입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugOutputStringEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetString](../../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md)|표시할 수 있는 메시지를 가져옵니다.|  
  
## 설명  
 예를 들어, 디버깅 중인 프로그램을 Win32 문자열 보낼 때 관리 되지 않는 코드에서 출력 될 문자열 시작 될 수 있습니다 `OutputDebugString` 함수입니다.  이 문자열 DE 여 가로채서 SDM로 전송의 `IDebugOutputStringEvent2` 이벤트입니다.  
  
 사용 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md) 사용자 응답을 요구 하는 메시지를 보낼 수 있습니다.  
  
 사용 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md) 에 대 한 응답을 요구 하지 않는 오류 메시지를 보낼 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)