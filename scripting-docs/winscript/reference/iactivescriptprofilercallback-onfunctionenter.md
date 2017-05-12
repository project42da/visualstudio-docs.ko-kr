---
title: "IActiveScriptProfilerCallback::OnFunctionEnter | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptProfilerCallback.OnFunctionEnter
apilocation: scrobj.dll
ms.assetid: 12dab2b4-df4e-444d-99cb-25e1c278e6e8
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IActiveScriptProfilerCallback::OnFunctionEnter
프로파일러 개체를 스크립팅 엔진 문서 개체 모델 \(DOM\)에 대 한 호출 되지 않는 함수 호출을 실행 하는 것을 알립니다.  
  
## 구문  
  
```  
HRESULT OnFunctionEnter(  
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
 DOM 호출에 대 한 스크립트 엔진이 호출 [IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md) 대신 `IActiveScriptProfilerCallback::OnFunctionEnter`.  많은 수의 고유한 메서드 및 속성의 DOM 때문입니다.  
  
## 참고 항목  
 [IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)   
 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)