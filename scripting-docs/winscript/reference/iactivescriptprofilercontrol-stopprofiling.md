---
title: "IActiveScriptProfilerControl::StopProfiling | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptProfilerControl.StopProfiling
apilocation: scrobj.dll
ms.assetid: 23b46ed6-a398-44c0-bc49-bf122e697cfe
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IActiveScriptProfilerControl::StopProfiling
스크립팅 엔진의 프로 파일링을 중지 합니다.  이 메서드를 호출 합니다. [IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md) 프로파일러 개체 및이 해제 합니다.  
  
## 구문  
  
```  
HRESULT StopProfiling(  
    [in] HRESULT hrShutdownReason);  
```  
  
#### 매개 변수  
 `hrShutdownReason`  
 \[in\] HRESULT 매개 변수로 전달 하는 [IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md) 프로파일러 개체의 메서드를.  
  
## 반환 값  
 HRESULT를 반환합니다.  다음과 같은 값을 사용할 수 있습니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`ACTIVPROF_E_PROFILER_ABSENT`|프로 파일링을 사용할 수 없습니다.|  
  
## 참고 항목  
 [IActiveScriptProfilerControl 인터페이스](../../winscript/reference/iactivescriptprofilercontrol-interface.md)