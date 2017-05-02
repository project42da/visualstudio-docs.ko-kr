---
title: "IActiveScriptProfilerCallback::OnFunctionExit | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptProfilerCallback.OnFunctionExit
apilocation: scrobj.dll
ms.assetid: a5d21715-2b0b-423e-8644-f04a9e7cde3d
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IActiveScriptProfilerCallback::OnFunctionExit
함수 실행이 완료 된 스크립팅 엔진을 호출 하는 개체에는 DOM \(문서 개체 모델\) 호출 아닙니다 프로파일러에 알립니다.  
  
## 구문  
  
```  
HRESULT OnFunctionExit(  
    [in] PROFILER_TOKEN scriptId,   
    [in] PROFILER_TOKEN functionId);  
```  
  
#### 매개 변수  
 `scriptId`  
 \[in\] 포함 함수는 스크립트의 고유 ID입니다.  이 ID는 스크립팅 엔진에 의해 할당 됩니다.  
  
 `functionId`  
 \[in\] 함수의 고유 ID입니다.  이 ID는 스크립팅 엔진에 의해 할당 됩니다.  
  
## 반환 값  
 이 메서드의 반환 값은 스크립트 엔진에 의해 무시 됩니다.  
  
## 설명  
 DOM 호출에 대 한 스크립트 엔진이 호출 [IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md) 대신 `IActiveScriptProfilerCallback::OnFunctionExit`.  많은 수의 고유한 메서드 및 속성의 DOM 때문입니다.  
  
## 참고 항목  
 [IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md)   
 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)