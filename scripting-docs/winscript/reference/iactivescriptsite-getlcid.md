---
title: IActiveScriptSite::GetLCID | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptSite.GetLCID
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_GetLCID
ms.assetid: 7b4a2dc1-bcf6-4bbf-884e-97b305a28eb7
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a6e128f5ac5de11b45af59c83750411c35e6efa7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsitegetlcid"></a>IActiveScriptSite::GetLCID
호스트의 사용자 인터페이스와 연결 된 로캘 식별자를 검색 합니다. 스크립팅 엔진의 식별자를 사용 하 여 오류 문자열 및 기타 사용자 인터페이스 요소는 엔진에 의해 생성 된 해당 언어로 표시 되도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetLCID(  
    LCID *plcid  // address of variable for language identifier  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `plcid`  
 [out] 주소 스크립팅 엔진에서 표시 하는 사용자 인터페이스 요소에 대 한 로캘 식별자를 수신 하는 변수입니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_NOTIMPL`|이 메서드가 구현되지 않았습니다. 시스템에서 정의한 로캘을 사용 합니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드가 반환 하는 경우 `E_NOTIMPL`, 시스템에서 정의한 로캘 식별자를 사용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)