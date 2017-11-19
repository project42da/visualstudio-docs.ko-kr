---
title: IActiveScript::GetScriptThreadID | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScript.GetScriptThreadID
apilocation: scrobj.dll
helpviewer_keywords: IActiveScript_GetScriptThreadID
ms.assetid: 2595d76e-30b5-429f-88b4-1d026645dd9b
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8850319035b7b5e3a9cbbd4bbe4340e1eefacc96
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptgetscriptthreadid"></a>IActiveScript::GetScriptThreadID
지정 된 Win32 스레드와 연결 된 스레드에 대 한 스크립팅 엔진 정의 식별자를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetScriptThreadID(  
    DWORD dwWin32ThreadID,       // Win32 thread identifier.  
    SCRIPTTHREADID *pstidThread  // Receives scripting thread. identifier  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwWin32ThreadID` ,  
 [in] 현재 프로세스에서 실행 중인 Win32 스레드의 스레드 식별자입니다. 사용 하 여는 [IActiveScript::GetCurrentScriptThreadID](../../winscript/reference/iactivescript-getcurrentscriptthreadid.md) 함수를 현재 실행 중인 스레드의 스레드 식별자를 검색 합니다.  
  
 `pstidThread` ,  
 [out] 주소 지정 Win32 스레드와 연결 된 스크립트 스레드 식별자를 수신 하는 변수입니다. 이 식별자에 대 한 해석은 스크립팅 엔진에 남아 있지만 Windows 스레드 식별자의 복사본이 수 있습니다. 참고 Win32 스레드를 종료 하는 경우이 식별자 할당 되지 않은 되 고 이후에 다른 스레드가 할당 될 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진에 로드 되거나 않은 초기화) 및 않아 실패 했습니다.|  
  
## <a name="remarks"></a>설명  
 검색 된 식별자 스크립트 스레드 실행 제어 방법에 대 한 후속 호출에서와 같은 사용할 수 있습니다는 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) 메서드.  
  
 호스트 개체 또는 비 기반 설명선 발생 하지 않고 기본이 아닌 스레드에서이 메서드를 호출할 수 있습니다는 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)