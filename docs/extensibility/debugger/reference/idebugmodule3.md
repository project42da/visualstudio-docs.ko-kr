---
title: "IDebugModule3 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugModule3"
helpviewer_keywords: 
  - "IDebugModule3 인터페이스"
ms.assetid: 44f8e96e-9c59-4ffc-9a08-9c908a0e4de7
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugModule3
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 기호와 JustMyCode 상태의 대체 위치를 지 원하는 모듈을 나타냅니다.  
  
## 구문  
  
```  
IDebugModule3 : IDebugModule2  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\)이 심볼의 대체 위치를 지원 하 고 작업으로 JustMyCode 상태이 인터페이스 구현 \(참조는 [Visual Studio 디버거 용어집](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md) "JustMyCode"의 정의 대 한\).  
  
## 호출자에 대 한 참고 사항  
 호출을 [GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md) 이 인터페이스를 반환 합니다.  DE 센드는 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md) 인터페이스를 사용 하 여 세션 디버그 매니저 \(SDM\)에 있는 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 메서드.  또한 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) 인터페이스는이 인터페이스를 반환 합니다.  
  
## 메서드에서 Vtable 순서  
 메서드 외에 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)|기호 및 각 경로 검색 한 결과를 검색 하는 경로 목록을 반환 합니다.|  
|[LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)|로드 하 고 현재 모듈에 대 한 기호를 초기화 합니다.|  
|[IsUserCode](../../../extensibility/debugger/reference/idebugmodule3-isusercode.md)|반환 플래그 모듈에서 사용자 코드를 나타내는지 여부를 지정 합니다.|  
|[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugmodule3-setjustmycodestate.md)|모듈 또는 하지 사용자 코드가 고려 되는지 여부를 지정 합니다.|  
  
## 설명  
 Visual Studio이 인터페이스의 일반적인 소비자입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)   
 [GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)