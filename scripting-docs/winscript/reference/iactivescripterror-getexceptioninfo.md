---
title: IActiveScriptError::GetExceptionInfo | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptError.GetExceptionInfo
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptError_GetExceptionInfo
ms.assetid: 528416cc-8468-4ad7-a6c2-fa1daf6ecf33
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8719d1a169c89d7b6cf712a125b6962b9c7a8839
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescripterrorgetexceptioninfo"></a>IActiveScriptError::GetExceptionInfo
스크립팅 엔진을 스크립트를 실행 하는 동안 발생 한 오류에 대 한 정보를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetExceptionInfo(  
    EXCEPINFO *pexcepinfo  // structure for exception information  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pexcepinfo`  
 [out] 주소는 `EXCEPINFO` 구조체 오류 정보입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 하면 또는 `E_FAIL` 오류가 발생 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)