---
title: "IDebugSymbolSearchEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugSymbolSearchEvent2"
helpviewer_keywords: 
  - "IDebugSymbolSearchEvent2"
ms.assetid: 9b946d55-ff85-44eb-b40a-efbf8282eafd
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugSymbolSearchEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 엔진 \(DE\) 디버깅 기호가 디버깅 되 고 있는 모듈에 대해 로드 된 나타내기 위해 전송 됩니다.  
  
## 구문  
  
```  
IDebugSymbolSearchEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE 보고 모듈의 기호를 로드 하려면이 인터페이스를 구현 합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 DE 만들고 보고 모듈의 기호를 로드 하려면이 이벤트 개체를 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 되는 콜백 함수입니다.  
  
## 메서드에서 Vtable 순서  
 `IDebugSymbolSearchEvent2` 인터페이스에 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)|기호 검색에 대 한 정보를 검색합니다.|  
  
## 설명  
 기호를 로드할 수 없습니다 경우에이 이벤트가 전송 됩니다.  호출 `IDebugSymbolSearchEvent2::GetSymbolSearchInfo` 실제로 모듈 기호가 있는지 확인 하려면이 이벤트의 처리기에 있습니다.  
  
 Visual Studio 일반적으로 사용이 이벤트 상태에서 로드 된 기호를 업데이트 하는  **모듈** 창입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)