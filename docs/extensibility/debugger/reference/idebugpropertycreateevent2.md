---
title: "IDebugPropertyCreateEvent2 | Microsoft Docs"
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
  - "IDebugPropertyCreateEvent2"
helpviewer_keywords: 
  - "IDebugPropertyCreateEvent2 인터페이스"
ms.assetid: 33b3082b-a42e-488a-a1e4-dadf506f922c
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugPropertyCreateEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

특정 문서와 연결 된 속성을 만들 때이 인터페이스는 디버그 엔진 \(DE\) 세션 디버그 매니저 \(SDM\) 전송 됩니다.  
  
## 구문  
  
```  
IDebugPropertyCreateEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE 속성 생성 되었음을 보고 하려면이 인터페이스를 구현 합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  이 인터페이스는 DE 로드 하거나 생성 하는 스크립트와 관련 된 속성을 작성 한 경우 및 해당 스크립트가 IDE에 표시 해야 할 경우에 구현 됩니다.  
  
## 호출자에 대 한 참고 사항  
 DE 만들고이 이벤트 객체 속성 작성 된 보고서를 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 되 면 SDM가 제공 되는 콜백 함수입니다.  
  
## 메서드에서 Vtable 순서  
 메서드를 다음 표에 나와 있는 `IDebugPropertyCreateEvent2` 인터페이스입니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugpropertycreateevent2-getdebugproperty.md)|새 속성을 가져옵니다.|  
  
## 설명  
 특정 문서 또는 연결 된 스크립트는 속성을 가진 경우는 DE이이 이벤트 SDM을 업데이트 하기 위해 보낼 수 있습니다의  **스크립트 문서** 창에 문서.  호출 하는 SDM [GetExtendedInfo](../../../extensibility/debugger/reference/idebugproperty2-getextendedinfo.md) 인수로 `guidDocument` 를 검색 하는 `VARIANT` 포함 하는 [IUnknown](/visual-cpp/atl/iunknown) 포인터입니다.  호출 하는 SDM [QueryInterface](/visual-cpp/atl/queryinterface) 에서이 포인터를 검색 하는 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) 를 업데이트 하는 데 사용 되는 인터페이스는  **스크립트 문서** 창입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)