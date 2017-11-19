---
title: IActiveScriptProfilerControl::StopProfiling | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptProfilerControl.StopProfiling
apilocation: scrobj.dll
ms.assetid: 23b46ed6-a398-44c0-bc49-bf122e697cfe
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63d837b0f7a59b1e3efc832c4d98cb7dcab5447c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercontrolstopprofiling"></a>IActiveScriptProfilerControl::StopProfiling
스크립팅 엔진에서 프로 파일링을 중지 합니다. 이 메서드를 호출 [IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md) 프로파일러 개체에 대 한 다음 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StopProfiling(  
    [in] HRESULT hrShutdownReason);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hrShutdownReason`  
 [in] HRESULT에 대 한 매개 변수로 전달할 수는 [IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md) 프로파일러 개체의 메서드.  
  
## <a name="return-value"></a>반환 값  
 HRESULT를 반환 합니다. 다음과 같은 값을 사용할 수 있습니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|메서드가 성공했으며|  
|`ACTIVPROF_E_PROFILER_ABSENT`|프로 파일링 사용 되지 않습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptProfilerControl 인터페이스](../../winscript/reference/iactivescriptprofilercontrol-interface.md)