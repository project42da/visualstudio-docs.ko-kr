---
title: "IDebugBeforeSymbolSearchEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugBeforeSymbolSearchEvent2 인터페이스"
ms.assetid: 679fd7b1-765a-41a8-a046-63240c09a499
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugBeforeSymbolSearchEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\)이이 인터페이스 세션 디버그 관리자 \(SDM\) 상태를 설정 하려면 메시지 표시줄 기호 로드 중 보냅니다.  
  
## 구문  
  
```  
IDebugBeforeSymbolSearchEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 기호 로드가 동안 상태 표시줄 메시지를 설정 해야 하는 경우는 DE이이 인터페이스를 구현 합니다.  이 인터페이스는 작업 또는 스크립트 인터프리터에 포함 된 디버그 엔진에만 구현 됩니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다 \(SDM을 사용 하 여  **QueryInterface** 액세스 하는  **IDebugEvent2** 인터페이스\)입니다.  
  
## 호출자에 대 한 참고 사항  
 DE 만들고 심볼 로드 시 상태 표시줄 메시지를 설정 해야 하는 경우이 이벤트 개체를 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 콜백 함수 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 합니다.  
  
## 메서드  
 다음 표에서 메서드를 `IDebugBeforeSymbolSearchEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetModuleName](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2-getmodulename.md)|현재 디버깅 중인 모듈의 이름을 검색 합니다.|  
  
## 요구 사항  
 헤더: Msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll