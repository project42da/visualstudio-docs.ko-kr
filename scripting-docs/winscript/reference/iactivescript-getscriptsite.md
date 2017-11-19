---
title: IActiveScript::GetScriptSite | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScript.GetScriptSite
apilocation: scrobj.dll
helpviewer_keywords: IActiveScript_GetScriptSite
ms.assetid: 83a2a89d-93d0-4cbd-9244-91a730cb406b
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 961483d45c72018bc216306d6c1aba0400a367ad
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptgetscriptsite"></a>IActiveScript::GetScriptSite
Windows 스크립트 엔진와 연결 된 사이트 개체를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetScriptSite(  
    REFIID iid,           // interface identifier  
    void **ppvSiteObject  // address of host site interface  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 요청된 된 인터페이스의 식별자입니다.  
  
 `ppvSiteObject`  
 [out] 주소를 호스트의 사이트 개체에 대 한 인터페이스 포인터를 받는 위치입니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_INVALIDARG`|인수가 올바르지 않습니다.|  
|`E_NOINTERFACE`|지정된 된 인터페이스를 지원 되지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`S_FALSE`|설정한 사이트가 없습니다. `ppvSiteObject` 로 설정 된 `NULL`합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)