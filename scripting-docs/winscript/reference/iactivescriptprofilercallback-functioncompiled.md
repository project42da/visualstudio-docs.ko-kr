---
title: "IActiveScriptProfilerCallback::FunctionCompiled | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptProfilerCallback.FunctionCompiled
apilocation: scrobj.dll
ms.assetid: a7e9ef17-3891-4731-9d08-c37bc489be61
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptProfilerCallback::FunctionCompiled
스크립트를 컴파일하는 경우 함수 개체는 스크립팅 엔진을 발생 프로파일러에 알립니다.  
  
## 구문  
  
```  
HRESULT FunctionCompiled(  
    [in] PROFILER_TOKEN functionId,  
    [in] PROFILER_TOKEN scriptId,  
    [in] [string] const WCHAR *pwszFunctionName,  
    [in] [string] const WCHAR *pwszFunctionNameHint,  
    [in] IUnknown *pIDebugDocumentContext);  
```  
  
#### 매개 변수  
 `functionId`  
 \[in\] 함수의 고유 ID입니다.  이 ID는 스크립팅 엔진에 의해 할당 됩니다.  
  
 `scriptId`  
 \[in\] 포함 함수는 스크립트의 고유 ID입니다.  
  
 `pwszFunctionName`  
 \[in\] 익명 함수에 대 한 이름, 함수 또는 null입니다.  
  
 `pwszFunctionNameHint`  
 \[in\] 유추 된 이름 함수 또는 스크립트 이름에서 추정 되지 않는 경우 null입니다.  
  
 `pIDebugDocumentContext`  
 \[in\] 가능한 경우 포인터는 `IUnknown` 프로파일러를 쿼리해야 하는 인터페이스는 [IDebugDocumentContext 인터페이스](../../winscript/reference/idebugdocumentcontext-interface.md) 포인터.  그렇지 않으면 null입니다.  
  
## 반환 값  
 이 메서드의 반환 값은 스크립트 엔진에 의해 무시 됩니다.  
  
## 설명  
 스크립팅 엔진만이 호스트에서 지 원하는 경우 문서 컨텍스트를 제공할 수 있습니다.  
  
## 참고 항목  
 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)