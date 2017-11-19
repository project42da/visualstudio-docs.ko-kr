---
title: IActiveScriptProfilerCallback::OnFunctionEnter | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptProfilerCallback.OnFunctionEnter
apilocation: scrobj.dll
ms.assetid: 12dab2b4-df4e-444d-99cb-25e1c278e6e8
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d9af9dc5ce1f4cb0eb5c328c90c20184111afd9b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercallbackonfunctionenter"></a>IActiveScriptProfilerCallback::OnFunctionEnter
스크립팅 엔진 문서 개체 모델 (DOM)에 대 한 호출 하지 않은 함수 호출을 실행 하려고 하는 프로파일러 개체를 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OnFunctionEnter(  
    [in] PROFILER_TOKEN scriptId,   
    [in] PROFILER_TOKEN functionId);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `scriptId`  
 [in] 함수가 포함 된 스크립트의 고유 ID입니다. 이 ID는 스크립팅 엔진에 의해 할당 됩니다.  
  
 `functionId`  
 [in] 함수의 고유 ID입니다. 이 ID는 스크립팅 엔진에 의해 할당 됩니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드의 반환 값은 스크립팅 엔진에서 무시 됩니다.  
  
## <a name="remarks"></a>설명  
 DOM 호출에 대 한 스크립팅 엔진 호출 [IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md) 대신 `IActiveScriptProfilerCallback::OnFunctionEnter`합니다. Dom의 고유한 메서드 및 속성 수가 많기 때문에 이것이  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)   
 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)