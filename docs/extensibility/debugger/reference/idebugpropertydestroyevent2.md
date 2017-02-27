---
title: "IDebugPropertyDestroyEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPropertyDestroyEvent2"
helpviewer_keywords: 
  - "IDebugPropertyDestroyEvent2 인터페이스"
ms.assetid: 301b7a75-ecfa-46f1-9131-66cf3e4be147
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugPropertyDestroyEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

특정 문서와 연결 된 속성이 소멸 될 때이 인터페이스는 디버그 엔진 \(DE\) 세션 디버그 매니저 \(SDM\) 전송 됩니다.  
  
## 구문  
  
```  
IDebugPropertyDestroyEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE 속성 소멸 되었음을 보고 하려면이 인터페이스를 구현 합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  이 인터페이스는 DE 스크립트와 관련 된 속성이 이전에 만든 경우에 구현 됩니다. 속성을 파괴 관련된 스크립트를 IDE에서 제거 합니다.  
  
## 호출자에 대 한 참고 사항  
 DE 만들고이 이벤트 개체가 소멸 된 속성이 보고서에 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 되 면 SDM가 제공 되는 콜백 함수입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugPropertyDestroyEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugpropertydestroyevent2-getdebugproperty.md)|멸망 하는 속성을 가져옵니다.|  
  
## 설명  
 설명 부분을 참조 하십시오. [IDebugPropertyCreateEvent2](../../../extensibility/debugger/reference/idebugpropertycreateevent2.md) 그 이유에 대 한 자세한 내용은이 이벤트를 사용할 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugPropertyCreateEvent2](../../../extensibility/debugger/reference/idebugpropertycreateevent2.md)