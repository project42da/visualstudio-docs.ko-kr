---
title: IActiveScriptProfilerCallback2::OnFunctionExitByName | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IActiveScriptProfilerCallback2::OnFunctionExitByName
ms.assetid: a6ddead4-e66d-4789-b778-84e5c343f908
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd26ab1cf36378c0f037d78a3c079c58e004006d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercallback2onfunctionexitbyname"></a>IActiveScriptProfilerCallback2::OnFunctionExitByName
엔진의 스크립팅 개체는 DOM 문서 개체 모델 () 함수 호출 실행을 완료 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OnFunctionExitByName(  
    [in] [string] const WCHAR *pwszFunctionName,  
    [in] PROFILER_SCRIPT_TYPE scriptType);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pwszFunctionName`  
 [in] 스크립팅 엔진 실행이 완료 되는 함수의 이름입니다.  
  
 `scriptType`  
 [in] 함수의 형식입니다. 유효한 값의 설명은 참조 하세요. [PROFILER_SCRIPT_TYPE 열거형](../../winscript/reference/profiler-script-type-enumeration.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드의 반환 값은 스크립팅 엔진에서 무시 됩니다.  
  
## <a name="remarks"></a>설명  
 스크립팅 엔진 DOM 호출에 대 한 호출 하는 대신이 메서드를 호출 [IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)합니다. Dom의 고유한 메서드 및 속성 수가 많기 때문에 이것이  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)   
 [IActiveScriptProfilerCallback2 인터페이스](../../winscript/reference/iactivescriptprofilercallback2-interface.md)