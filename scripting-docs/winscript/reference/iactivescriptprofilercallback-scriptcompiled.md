---
title: IActiveScriptProfilerCallback::ScriptCompiled | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptProfilerCallback.ScriptCompiled
apilocation: scrobj.dll
ms.assetid: 1bb8e9be-cbb1-4a61-b36c-805127a56ac7
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7ea1823087b323f2acc9b87edfce48bbe9f924bd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercallbackscriptcompiled"></a>IActiveScriptProfilerCallback::ScriptCompiled
개체의 스크립팅 엔진 하는 컴파일된 스크립트 프로파일러에 알립니다. 이 메서드는 컴파일되는 모든 스크립트에 대해 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ScriptCompiled(  
    [in] PROFILER_TOKEN scriptId,  
    [in] PROFILER_SCRIPT_TYPE type,  
    [in] IUnknown *pIDebugDocumentContext);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `scriptId`  
 [in] 컴파일된 스크립트의 고유 ID입니다. 이 ID는 스크립팅 엔진에 의해 할당 됩니다.  
  
 `type`  
 [in] 컴파일된 스크립트의 형식입니다. 값에 정의 된 [PROFILER_SCRIPT_TYPE 열거형](../../winscript/reference/profiler-script-type-enumeration.md)합니다.  
  
 `pIDebugDocumentContext`  
 [in] 사용 가능한 경우에 대 한 포인터는 `IUnknown` 프로파일러에 대해 쿼리해야 하는 인터페이스는 [IDebugDocumentContext 인터페이스](../../winscript/reference/idebugdocumentcontext-interface.md) 포인터입니다. 그렇지 않으면이 null이 됩니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드의 반환 값은 스크립팅 엔진에서 무시 됩니다.  
  
## <a name="remarks"></a>설명  
 이 호스트에서 지원 되는 경우에 스크립팅 엔진에서 문서 컨텍스트를 제공할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)