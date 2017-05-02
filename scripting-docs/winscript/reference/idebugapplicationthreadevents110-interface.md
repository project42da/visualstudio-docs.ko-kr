---
title: "IDebugApplicationThreadEvents110 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplicationThreadEvents110 인터페이스"
ms.assetid: 91a98b0e-7c81-4118-af75-82f75fd4f25a
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IDebugApplicationThreadEvents110 인터페이스
더 많은 스레드 이벤트를 추가합니다.  이러한 이벤트는 로컬만 있습니다.  즉, 프로세스 중에 구독 수 디버깅 하 고 사용 하는 [특수 한](http://go.microsoft.com/fwlink/?LinkId=232738) 싱 및 PDM 응용 프로그램 스레드가 개체의 메서드 싱 \(개체를 해당 구현 [IDebugApplicationThread 인터페이스](../../winscript/reference/idebugapplicationthread-interface.md)\).  가 발생 하는 스레드에서 발생 합니다.  
  
> [!IMPORTANT]
>  V11.0 PDM 및 큰이 인터페이스를 구현 합니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 메서드  
 `IDebugActivationThreadEvents110` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IDebugApplicationThreadEvents110 ::OnBeginThreadRequest](../../winscript/reference/idebugapplicationthreadevents110-onbeginthreadrequest.md)|호출 전환 PDM의 스레드를 사용 하 여 스레드를 시작 했습니다.|  
|[IDebugApplicationThreadEvents110::OnResumeFromBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onresumefrombreakpoint.md)|스레드가 중단점에서 다시 시작 하 고 하 고 다시 활성화 됩니다.|  
|[IDebugApplicationThreadEvents110::OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md)|스레드가 중단점을 중단 하 고 한 스레드가 완전히 중단 해야 하는 호출을 처리할 수 있습니다.|  
|[IDebugApplicationThreadEvents110::OnThreadRequestComplete](../../winscript/reference/idebugapplicationthreadevents110-onthreadrequestcomplete.md)|호출 PDM의 스레드를 사용 하 여 스레드를 전환 완료 했습니다.|