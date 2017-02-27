---
title: "IDebugLoadCompleteEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugLoadCompleteEvent2"
helpviewer_keywords: 
  - "IDebugLoadCompleteEvent2"
ms.assetid: 37eb7360-28e9-4273-862a-4c17f22af690
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugLoadCompleteEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 엔진 \(DE\) 세션 디버그 매니저 \(SDM\) 프로그램을 로드 하면 되지만 코드를 실행 하기 전에 전송 됩니다.  
  
## 구문  
  
```  
IDebugLoadCompleteEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE 프로그램이 성공적으로 로드 되었음을 보고 하기 위해이 인터페이스를 구현 합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 DE 만들고 프로그램이 성공적으로 로드 되었음을 보고 하려면이 이벤트 개체를 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 되는 콜백 함수입니다.  
  
## 설명  
 중지 이벤트는이 이벤트 하 고 있어야 합니다을 `EVENT_STOPPING` 는 이벤트 특성에 설정 된 플래그를 지정 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)