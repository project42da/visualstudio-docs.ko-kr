---
title: IActiveScriptProfilerCallback::FunctionCompiled | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptProfilerCallback.FunctionCompiled
apilocation: scrobj.dll
ms.assetid: a7e9ef17-3891-4731-9d08-c37bc489be61
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 797476d4892224ad0b27c9caf579c0704693c835
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercallbackfunctioncompiled"></a>IActiveScriptProfilerCallback::FunctionCompiled
엔진의 스크립팅 개체는 스크립트를 컴파일하는 경우 함수에서 발생 했습니다 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FunctionCompiled(  
    [in] PROFILER_TOKEN functionId,  
    [in] PROFILER_TOKEN scriptId,  
    [in] [string] const WCHAR *pwszFunctionName,  
    [in] [string] const WCHAR *pwszFunctionNameHint,  
    [in] IUnknown *pIDebugDocumentContext);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] 함수의 고유 ID입니다. 이 ID는 스크립팅 엔진에 의해 할당 됩니다.  
  
 `scriptId`  
 [in] 함수가 포함 된 스크립트의 고유 ID입니다.  
  
 `pwszFunctionName`  
 [in] 익명 함수에 대 한 함수 또는 null의 이름입니다.  
  
 `pwszFunctionNameHint`  
 [in] 함수 또는 null 스크립팅 엔진 임의의 이름을 추론 하는 경우의 유추 된 이름입니다.  
  
 `pIDebugDocumentContext`  
 [in] 사용 가능한 경우에 대 한 포인터는 `IUnknown` 프로파일러에 대해 쿼리해야 하는 인터페이스는 [IDebugDocumentContext 인터페이스](../../winscript/reference/idebugdocumentcontext-interface.md) 포인터입니다. 그렇지 않으면 null입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드의 반환 값은 스크립팅 엔진에서 무시 됩니다.  
  
## <a name="remarks"></a>설명  
 이 호스트에서 지원 되는 경우에 스크립팅 엔진에서 문서 컨텍스트를 제공할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)