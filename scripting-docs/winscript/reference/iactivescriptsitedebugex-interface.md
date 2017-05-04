---
title: "IActiveScriptSiteDebugEx 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptSiteDebugEx 인터페이스"
ms.assetid: 76869378-1a7b-47bd-8cd0-acc31f91d58d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptSiteDebugEx 인터페이스
와 함께이 인터페이스는 `IActiveScriptSiteDebug` 인터페이스 응용 프로그램에서 런타임 오류에 대 한 알림을 표시 하 고 선택적으로 응용 프로그램 디버깅에 대 한 연결 하는 데 필요한 호스트를 작성 하는 경우.  프로세스 디버그 관리자 알림을 통해 제공 `IActiveScriptDebug` 스크립트는에서 Just\-in\-time 디버거로 경우 컴퓨터에서 찾을 수 있습니다.  스크립트 없음에서 Just\-in\-time 디버거로 찾은 PDM의 알림을 통해 제공 경우 `IActiveScriptDebugEx` 대신 합니다.  
  
 런타임 오류에 대 한 알림을 받으려면 호스트 처리 해야 [ActiveScriptSiteDebug::OnScriptErrorDebug](http://msdn.microsoft.com/ko-kr/cf7639f9-a699-4571-9f3a-82ef52c0b5f4).  사용자 작업을 기반으로 다음 내부 디버거 및 반환을 연결 하거나 반환할 Onscripterrordebug는 디버거에서 시작 결정할 수 `pfEnterDebugger` 매개 변수.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug](../../winscript/reference/iactivescriptsitedebugex-oncannotjitscripterrordebug.md)|호스트 관리자는 프로세스를 디버깅할 때 스크립트 런타임 오류에 대 한 외부 Just In Time 디버거에 찾지 알립니다.|