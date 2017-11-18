---
title: IActiveScriptProfilerControl2::PrepareProfilerStop | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IActiveScriptProfilerControl2::PrepareProfilerStop
ms.assetid: e43a63bc-c44f-44a8-9db4-29062b9e6a16
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 78078cd874be1d7d3d169be2d3d70e65866be3fd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercontrol2prepareprofilerstop"></a>IActiveScriptProfilerControl2::PrepareProfilerStop
적용 가능한 모든 스크립팅 엔진에서 프로 파일링을 중지 하려는 프로파일러에 알립니다. 이 방법을 사용 하면 얻을 수 경우 완전 한 호출 스택이 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 프로 파일링을 중지 하는 경우를 실행 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT PrepareProfilerStop();  
```  
  
#### <a name="parameters"></a>매개 변수  
 메서드는 매개 변수를 사용 하지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 HRESULT를 반환 합니다. 다음과 같은 값을 사용할 수 있습니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|프로 파일링을 시작할 수 없습니다.|  
|`S_FALSE`|프로 파일링 스크립트가 실행 되지 않는 경우 중지 되었습니다.|  
|`ACTIVPROF_E_PROFILER_ABSENT`|프로 파일링 사용 되지 않습니다.|  
  
## <a name="remarks"></a>설명  
 호출 `IActiveScriptProfilerControl2::PrepareProfilerStop` 호출 스택에 있는 함수에 대 한 이벤트 전송 되는지 확인 합니다. 이 메서드는 현재 탭에 있는 모든 스크립팅 엔진에서 프로 파일링을 중지 하기 전에 호출 됩니다. 모든 스크립팅 엔진에 대 한 메서드를 호출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md)   
 [IActiveScriptProfilerControl2 인터페이스](../../winscript/reference/iactivescriptprofilercontrol2-interface.md)