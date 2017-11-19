---
title: IActiveScriptError::GetSourcePosition | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptError.GetSourcePosition
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptError_GetSourcePosition
ms.assetid: ae9b26b1-82a7-4645-9686-3261d8248664
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d63310a8ba5cfda39d48a482eaf7c345cd492adc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescripterrorgetsourceposition"></a>IActiveScriptError::GetSourcePosition
스크립팅 엔진을 스크립트를 실행 하는 동안 오류가 발생 하는 소스 코드의 위치를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSourcePosition(  
    DWORD *pdwSourceContext,  // context cookie  
    ULONG *pulLineNumber,     // line number of error  
    LONG *pichCharPosition    // character position of error  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwSourceContext`  
 [out] 주소는 컨텍스트를 식별 하는 쿠키를 수신 하는 변수입니다. 이 매개 변수 해석을 호스트 응용 프로그램에 따라 달라 집니다.  
  
 `pulLineNumber`  
 [out] 오류가 발생 한 소스 파일의 줄 번호를 수신 하는 변수의 주소입니다.  
  
 `pichCharPosition`  
 [out] 오류가 발생 한 줄의 문자 위치를 수신 하는 변수의 주소입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 하면 또는 `E_FAIL` 경우 위치를 검색 하지 못했습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)