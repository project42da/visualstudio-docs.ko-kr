---
title: IActiveScript::SetScriptSite | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScript.SetScriptSite
apilocation: scrobj.dll
helpviewer_keywords: IActiveScript_SetScriptSite
ms.assetid: 47d94c32-09f8-4539-ac56-0236026f627b
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 11fa9003abb03c42adcbf3a548bb5b90d763a344
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsetscriptsite"></a>IActiveScript::SetScriptSite
스크립팅 엔진 알립니다는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 인터페이스 사이트 호스트에서 제공 합니다. 다른 모든 하기 전에이 메서드를 호출 [IActiveScript](../../winscript/reference/iactivescript.md) 인터페이스 메서드를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetScriptSite(  
    IActiveScriptSite *pScriptSite  // address of host script site  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pScriptSite`  
 [in] 스크립팅 엔진의이 인스턴스와 연결 되도록 스크립트 호스트에서 제공한 사이트의 주소입니다. 이 스크립팅 엔진 인스턴스가;에 사이트를 고유 하 게 할당 되어야 합니다. 다른 스크립팅 엔진와 공유할 수 없습니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_FAIL`|지정 되지 않은 오류가 발생 했습니다. 스크립팅 엔진에서 사이트 초기화를 완료 하지 못했습니다.|  
|`E_INVALIDARG`|인수가 올바르지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 사이트를 이미 설정한).|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)