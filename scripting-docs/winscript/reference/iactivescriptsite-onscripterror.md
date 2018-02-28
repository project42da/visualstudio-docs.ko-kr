---
title: IActiveScriptSite::OnScriptError | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptSite.OnScriptError
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnScriptError
ms.assetid: 5c9c85cc-21ad-4232-be83-a24cc7570108
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4ae066fe7fa04a5c97dec618c65ccee3f90984a0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsiteonscripterror"></a>IActiveScriptSite::OnScriptError
엔진을 스크립트를 실행 하는 동안 실행 오류가 발생 했음을 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OnScriptError(  
    IActiveScriptError *pase  // address of error interface  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pase`  
 [in] Error 개체의 주소 [IActiveScriptError](../../winscript/reference/iactivescripterror.md) 인터페이스입니다. 호스트가이 인터페이스를 사용 하 여 실행 오류에 대 한 정보를 얻을 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 올바르게 오류를 처리 하거나 OLE 그렇지 않은 경우 오류 코드를 정의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)