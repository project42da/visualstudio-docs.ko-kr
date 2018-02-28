---
title: IActiveScript::GetScriptThreadState | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScript.GetScriptThreadState
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptThreadState
ms.assetid: 7cac94d0-436e-4c29-895b-0c4afa0b3ccc
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b11b8566857bc70aaeac5bdf8e8e357fa5d9c2e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptgetscriptthreadstate"></a>IActiveScript::GetScriptThreadState
스크립트 스레드의 현재 상태를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetScriptThreadState(  
    SCRIPTTHREADID stidThread,    // identifier of script thread  
    SCRIPTTHREADSTATE *pstsState  // receives state flag  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stidThread`  
 [in] 는 상태가 필요한는 스레드의 식별자 또는 다음과 같은 특수 스레드 식별자 중 하나:  
  
|값|의미|  
|-----------|-------------|  
|SCRIPTTHREADID_BASE|기본 스레드입니다. 즉,는 스크립팅 엔진 스레드 인스턴스화 되었습니다.|  
|SCRIPTTHREADID_CURRENT|현재 실행 중인 스레드입니다.|  
  
 `pstsState`  
 [out] 주소 지정된 된 스레드가의 상태를 수신 하는 변수입니다. 상태에 정의 된 명명 된 상수 값 중 하나에 의해 표시 됩니다는 [SCRIPTTHREADSTATE 열거형](../../winscript/reference/scriptthreadstate-enumeration.md) 열거 합니다. 이 매개 변수는 현재 스레드를 식별 하지 않으면 상태는 언제 든 지 변경 될 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진에 로드 되거나 않은 초기화).|  
  
## <a name="remarks"></a>설명  
 호스트 개체 또는 비 기반 설명선 발생 하지 않고 기본이 아닌 스레드에서이 메서드를 호출할 수 있습니다는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)