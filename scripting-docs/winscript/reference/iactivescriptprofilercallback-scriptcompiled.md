---
title: "IActiveScriptProfilerCallback::ScriptCompiled | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptProfilerCallback.ScriptCompiled
apilocation: scrobj.dll
ms.assetid: 1bb8e9be-cbb1-4a61-b36c-805127a56ac7
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptProfilerCallback::ScriptCompiled
스크립트 개체는 스크립트 엔진 컴파일 프로파일러에 알립니다.  이 메서드는 컴파일된 모든 스크립트가 호출 됩니다.  
  
## 구문  
  
```  
HRESULT ScriptCompiled(  
    [in] PROFILER_TOKEN scriptId,  
    [in] PROFILER_SCRIPT_TYPE type,  
    [in] IUnknown *pIDebugDocumentContext);  
```  
  
#### 매개 변수  
 `scriptId`  
 \[in\] 컴파일된 스크립트의 고유 ID입니다.  이 ID는 스크립팅 엔진에 의해 할당 됩니다.  
  
 `type`  
 \[in\] 컴파일된 스크립트의 형식입니다.  값에 정의 된 [PROFILER\_SCRIPT\_TYPE 열거형](../../winscript/reference/profiler-script-type-enumeration.md).  
  
 `pIDebugDocumentContext`  
 \[in\] 가능한 경우에 대 한 포인터는 `IUnknown` 프로파일러를 쿼리해야 하는 인터페이스는 [IDebugDocumentContext 인터페이스](../../winscript/reference/idebugdocumentcontext-interface.md) 포인터.  그렇지 않으면이 null입니다.  
  
## 반환 값  
 이 메서드의 반환 값은 스크립트 엔진에 의해 무시 됩니다.  
  
## 설명  
 스크립팅 엔진만이 호스트에서 지 원하는 경우 문서 컨텍스트를 제공할 수 있습니다.  
  
## 참고 항목  
 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)