---
title: "IActiveScriptProfilerControl 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1448b394-9743-41b5-8eb9-5026a45773a4
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IActiveScriptProfilerControl 인터페이스
프로 파일링을 지 원하는 스크립팅 엔진에 의해 구현 됩니다.  일반적으로 구현 하는 개체는 `IActiveScriptProfilerControl` 구현도 [IActiveScript](../../winscript/reference/iactivescript.md) 인터페이스.  이런 경우에 대 한 핸들을 얻을 수 있습니다는 `IActiveScriptProfilerControl` 를 호출 하 여 인터페이스는 `IUnknown::QueryInterface` 개체 메서드를.  스크립팅 엔진의 프로 파일링을 시작 하 고 중지 하는 방법에 대 한 필요한 메서드는 인터페이스를 제공 합니다.  
  
## 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptProfilerControl::StartProfiling](../../winscript/reference/iactivescriptprofilercontrol-startprofiling.md)|스크립팅 엔진의 프로 파일링을 시작 합니다.|  
|[IActiveScriptProfilerControl::SetProfilerEventMask](../../winscript/reference/iactivescriptprofilercontrol-setprofilereventmask.md)|프로파일러 이벤트 마스크 스크립팅 엔진에 설정합니다.|  
|[IActiveScriptProfilerControl::StopProfiling](../../winscript/reference/iactivescriptprofilercontrol-stopprofiling.md)|스크립팅 엔진의 프로 파일링을 중지 합니다.|  
  
## 참고 항목  
 [액티브 스크립트 프로파일러 인터페이스](../../winscript/reference/active-script-profiler-interfaces.md)