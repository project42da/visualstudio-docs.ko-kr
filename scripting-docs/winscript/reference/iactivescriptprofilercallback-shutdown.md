---
title: IActiveScriptProfilerCallback::Shutdown | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptProfilerCallback.Shutdown
apilocation: scrobj.dll
ms.assetid: 1281bf3c-d7d8-4ff5-9d8a-d1761fdb262e
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ec47cd5f581c36abb60b662983c6d806a4732f47
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercallbackshutdown"></a>IActiveScriptProfilerCallback::Shutdown
스크립팅 엔진에서 프로 파일링이 중지 될 때마다 프로파일러 개체를 알리기 위해 호출 됩니다. 이러한 방식으로 프로파일러 개체 수 루틴을 호출의 정리, 필요한 경우. 스크립팅 엔진을 종료 하거나를 호출할 때 스크립팅 엔진에서이 메서드 호출 또한 됩니다 [IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md) 실패 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Shutdown(  
    [in] HRESULT hrReason);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hrReason`  
 [in] 종료에 대 한 설명입니다. 스크립팅 엔진을 종료 하는 경우 `S_OK` 전달 됩니다. 경우에 대 한 호출 [IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md) HRESULT 전달 실패 HRESULT 반환 합니다. 이 값에서 검색 되 고, 그러지 [IActiveScriptProfilerControl::StopProfiling](../../winscript/reference/iactivescriptprofilercontrol-stopprofiling.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드의 반환 값은 스크립팅 엔진에서 무시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptProfilerCallback 인터페이스](../../winscript/reference/iactivescriptprofilercallback-interface.md)