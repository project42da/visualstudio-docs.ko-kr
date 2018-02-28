---
title: IActiveScript::GetCurrentScriptThreadID | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScript.GetCurrentScriptThreadID
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetCurrentScriptThreadID
ms.assetid: b09e8b48-4209-480e-8b71-e99ee9ae2e17
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5921dc4d0f9a9bf0d505fece0f47354cb16d440c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptgetcurrentscriptthreadid"></a>IActiveScript::GetCurrentScriptThreadID
현재 실행 중인 스레드에 대 한 스크립팅 엔진 정의 식별자를 검색합니다. 스크립트 스레드 실행 제어 방법에 대 한 후속 호출에서와 같은 식별자를 사용할 있습니다는 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCurrentScriptThreadID(  
    SCRIPTTHREADID *pstidThread  // receives scripting thread identifier  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pstidThread`  
 [out] 현재 스레드와 연결 된 스크립트 스레드 식별자를 수신 하는 변수의 주소입니다. 이 식별자에 대 한 해석은 스크립팅 엔진에 남아 있지만 Windows 스레드 식별자의 복사본이 수 있습니다. Win32 스레드를 종료 하는 경우에이 식별자 할당 되지 않은 되 고 이후에 다른 스레드를 할당할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 하면 또는 `E_POINTER` 포인터가 잘못 지정 되었습니다.  
  
## <a name="remarks"></a>설명  
 호스트 개체 또는 비 기반 설명선 발생 하지 않고 기본이 아닌 스레드에서이 메서드를 호출할 수 있습니다는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)