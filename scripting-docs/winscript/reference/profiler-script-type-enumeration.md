---
title: "PROFILER_SCRIPT_TYPE 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: PROFILER_SCRIPT_TYPE
apilocation: scrobj.dll
ms.assetid: 3ab6633a-6241-44f0-b837-14336f70c71e
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# PROFILER_SCRIPT_TYPE 열거형
스크립트의 형식을 지정합니다.  
  
## 구문  
  
```  
typedef enum {  
    PROFILER_SCRIPT_TYPE_USER,  
    PROFILER_SCRIPT_TYPE_DYNAMIC,  
    PROFILER_SCRIPT_TYPE_NATIVE,  
    PROFILER_SCRIPT_TYPE_DOM  
} PROFILER_SCRIPT_TYPE;  
```  
  
## Members  
  
|멤버|설명|  
|--------|--------|  
|PROFILER\_SCRIPT\_TYPE\_USER|사용자가 작성 하는 스크립트 코드를 지정합니다.|  
|PROFILER\_SCRIPT\_TYPE\_DYNAMIC|실행 중에 동적으로 생성 하는 스크립트 코드를 지정 합니다.|  
|PROFILER\_SCRIPT\_TYPE\_NATIVE|스크립팅 엔진에 의해 정의 된 개체와 네이티브 함수에 대 한 스크립트 형식을 지정 합니다.|  
|PROFILER\_SCRIPT\_TYPE\_DOM|에 DOM \(문서 개체 모델\)의 Internet Explorer, 예를 들어, 호출 하는 호출에 지정 된 `document.getElementById` 메서드.|  
  
## 참고 항목  
 [액티브 스크립트 프로파일러 상수, 열거형 및 구조체](../../winscript/reference/active-script-profiler-constants-enumerations-and-structures.md)   
 [IActiveScriptProfilerCallback::ScriptCompiled](../../winscript/reference/iactivescriptprofilercallback-scriptcompiled.md)   
 [IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)   
 [IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)