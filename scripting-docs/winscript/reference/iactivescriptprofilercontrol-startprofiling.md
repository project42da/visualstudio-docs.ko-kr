---
title: IActiveScriptProfilerControl::StartProfiling | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptProfilerControl.StartProfiling
apilocation: scrobj.dll
ms.assetid: 56a7b3b7-8c21-43d0-9d8b-53bbc19fabb9
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5362eaba439ff7a645a8323c4eed5d9496f6d88
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercontrolstartprofiling"></a>IActiveScriptProfilerControl::StartProfiling
스크립팅 엔진에서 프로 파일링을 시작 합니다. 스크립팅 엔진을 호출 하 여 프로파일러 개체의 인스턴스를 만들고 [CoCreateInstance](http://msdn.microsoft.com/en-us/7295a55b-12c7-4ed0-a7a4-9ecee16afdec)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StartProfiling(  
    [in] REFCLSID clsidProfilerObject,  
    [in] DWORD dwEventMask,  
    [in] DWORD dwContext);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `clsidProfilerObject`  
 [in] 클래스 식별자 (CLSID) 만들려는 프로파일러 개체입니다.  
  
 `dwEventMask`  
 [in] 이벤트 유형을 지정 하는 4 바이트 비트 마스크입니다. 에 정의 된 비트 [PROFILER_EVENT_MASK 열거형](../../winscript/reference/profiler-event-mask-enumeration.md)합니다.  
  
 `dwContext`  
 [in] 프로파일러 개체에 전달 되는 4 바이트 값입니다.  
  
## <a name="return-value"></a>반환 값  
 HRESULT를 반환 합니다. 다음과 같은 값을 사용할 수 있습니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|메서드가 성공했으며|  
|`ACTIVPROF_E_PROFILER_PRESENT`|프로 파일링 활성화 됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptProfilerControl 인터페이스](../../winscript/reference/iactivescriptprofilercontrol-interface.md)