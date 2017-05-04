---
title: "IActiveScriptProfilerCallback::Shutdown | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptProfilerCallback.Shutdown
apilocation: scrobj.dll
ms.assetid: 1281bf3c-d7d8-4ff5-9d8a-d1761fdb262e
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# IActiveScriptProfilerCallback::Shutdown
프로 파일링 스크립팅 엔진이 중지 될 때마다 프로파일러 개체에 알리기 위해 호출 됩니다.  이 따라서 필요한 경우 프로파일러 개체의 정리 루틴을 호출할 수 있습니다.  이 메서드는 스크립팅 엔진에서 스크립팅 엔진이 종료 또는 호출 하는 경우 라고도 [IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md) 오류가 발생 합니다.  
  
## 구문  
  
```  
HRESULT Shutdown(  
    [in] HRESULT hrReason);  
```  
  
#### 매개 변수  
 `hrReason`  
 \[in\] 시스템 종료 이유입니다.  스크립트를 종료 하는 경우 `S_OK` 전달 됩니다.  경우 호출을 [IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md) 실패 HRESULT 반환 된 HRESULT를 전달 합니다.  그렇지 않으면이 값에서 검색 됩니다 [IActiveScriptProfilerControl::StopProfiling](../../winscript/reference/iactivescriptprofilercontrol-stopprofiling.md).  
  
## 반환 값  
 이 메서드의 반환 값은 스크립트 엔진에 의해 무시 됩니다.  
  
## 참고 항목  
 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)