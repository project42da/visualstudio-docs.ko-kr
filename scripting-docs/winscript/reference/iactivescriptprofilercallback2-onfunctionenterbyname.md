---
title: "IActiveScriptProfilerCallback2::OnFunctionEnterByName | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptProfilerCallback2::OnFunctionEnterByName"
ms.assetid: 24b1593a-97fc-4d70-9b85-ec86fb59f987
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# IActiveScriptProfilerCallback2::OnFunctionEnterByName
프로파일러 개체를 문서 개체 모델 \(DOM\) 함수 호출을 실행 하려는 스크립트 엔진에 알립니다.  
  
## 구문  
  
```  
HRESULT OnFunctionEnterByName(  
    [in] [string] const WCHAR *pwszFunctionName,  
    [in] PROFILER_SCRIPT_TYPE scriptType);  
```  
  
#### 매개 변수  
 `pwszFunctionName`  
 \[in\] 스크립팅 엔진에서 실행 하려는 함수의 이름입니다.  
  
 `scriptType`  
 \[in\] 함수의 형식입니다.  유효한 값에 대 한 설명은 참조 하십시오. [PROFILER\_SCRIPT\_TYPE 열거형](../../winscript/reference/profiler-script-type-enumeration.md).  
  
## 반환 값  
 이 메서드의 반환 값은 스크립트 엔진에 의해 무시 됩니다.  
  
## 설명  
 DOM 호출에 대 한 스크립팅 엔진이이 메서드를 호출 하지 않고 호출 [IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md).  많은 수의 고유한 메서드 및 속성의 DOM 때문입니다.  
  
## 참고 항목  
 [IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)   
 [IActiveScriptProfilerCallback2 인터페이스](../../winscript/reference/iactivescriptprofilercallback2-interface.md)