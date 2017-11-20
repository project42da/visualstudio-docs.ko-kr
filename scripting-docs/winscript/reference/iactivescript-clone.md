---
title: IActiveScript::Clone | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScript.Clone
apilocation: scrobj.dll
helpviewer_keywords: IActiveScript_Clone
ms.assetid: aa000b2a-7085-448d-a422-f7adac7851cb
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4b0b83bcf86bcc56701d11f22640df966334697b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptclone"></a>IActiveScript::Clone
현재 스크립팅 엔진 (모든 현재 실행 상태), 빼기는 현재 스레드의 사이트가 있는 로드할된 스크립팅 엔진 반환을 복제 합니다. 이 새로운 스크립팅 엔진의 속성을 원래 스크립팅 엔진 것에 초기화 된 상태로 전환 된 경우 속성과 동일 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Clone(  
    IActiveScript **ppscript  // receives pointer to IActiveScript  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppscript`  
 [out] 에 대 한 포인터를 받는 변수의 주소는 [IActiveScript](../../winscript/reference/iactivescript.md) 복제 스크립팅 엔진의 인터페이스입니다. 호스트는 사이트와 호출 만들어야는 [IActiveScript::SetScriptSite](../../winscript/reference/iactivescript-setscriptsite.md) 메서드는 initialized 상태가 됩니다 새 스크립팅 엔진에서 그리고이 사용할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_NOTIMPL`|이 메서드는 지원되지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진에 로드 되거나 않은 초기화).|  
  
## <a name="remarks"></a>설명  
 `IActiveScript::Clone` 최적화 하는 방법은 `IPersist*::Save`, `CoCreateInstance`, 및 `IPersist*::Load`이므로 새 스크립팅 엔진의 상태 원래 스크립팅 엔진의 상태 저장 하 고 새 스크립팅 엔진에 로드 된 경우 처럼 동일한 이어야 합니다. 명명 된 항목 복제 스크립팅 엔진에 중복 된 하지만 각 항목에 대 한 특정 개체 포인터 기억 되 고 사용 하 여 가져온는 [IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md) 메서드. 이렇게 하면 스레드 진입점 (아파트 모델)을 사용할 수 있는 프로그램 동일한 개체 모델입니다.  
  
 이 메서드는 동일한 스크립트의 여러 인스턴스를 실행할 수 있는 다중 스레드 서버 호스트에 사용 됩니다. 스크립팅 엔진을 반환할 수 있습니다 `E_NOTIMPL`, 호스트 영구 상태를 복제 하 고 사용 하 여 스크립팅 엔진의 새 인스턴스를 생성 하 여 동일한 결과 얻을 수는 쿼리에서 `IPersist*` 인터페이스입니다.  
  
 호스트 개체 또는 비 기반 설명선 발생 하지 않고 기본이 아닌 스레드에서이 메서드를 호출할 수 있습니다는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)