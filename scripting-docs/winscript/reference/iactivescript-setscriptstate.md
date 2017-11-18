---
title: IActiveScript::SetScriptState | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScript.SetScriptState
apilocation: scrobj.dll
helpviewer_keywords: IActiveScript_SetScriptState
ms.assetid: f2b2700c-0c8d-40db-ad84-dc751c5d9bc2
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 146cd5e4f2b6137fc6fe6e32e8ca153c3aab8fd5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsetscriptstate"></a>IActiveScript::SetScriptState
지정 된 상태에 스크립팅 엔진을 추가합니다. 호스트 개체 또는 비 기반 설명선 발생 하지 않고 기본이 아닌 스레드에서이 메서드를 호출할 수 있습니다는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetScriptState(  
    SCRIPTSTATE ss  // identifier of new state  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ss`  
 [in] 스크립팅 엔진을 지정한 상태 설정합니다. 에 정의 된 값 중 하나일 수 있습니다는 [SCRIPTSTATE 열거형](../../winscript/reference/scriptstate-enumeration.md) 열거 합니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_FAIL`|스크립팅 엔진에서 초기화 된 상태로 전환을 지원 하지 않습니다. 호스트 해야이 스크립팅 엔진을 취소 및 만들기, 초기화 및 동일한 효과 달성 하기 위해 새 스크립팅 엔진을 로드 합니다.|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진에 로드 되거나 않은 초기화) 및 않아 실패 했습니다.|  
|`OLESCRIPT_S_PENDING`|메서드가 성공적으로 대기 하지만 상태가 아직 변경 되지 않습니다. 경우에 상태 변경을 사이트 콜백할 통해는 [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) 메서드.|  
|`S_FALSE`|메서드가 성공 했지만 스크립트가 이미 지정 된 상태에서입니다.|  
  
## <a name="remarks"></a>설명  
 스크립팅 엔진 상태에 대 한 자세한 내용은의 스크립트 엔진 상태 섹션을 참조 하십시오. [Windows 스크립트 엔진](../../winscript/windows-script-engines.md) 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript::Clone](../../winscript/reference/iactivescript-clone.md)   
 [IActiveScript::GetScriptDispatch](../../winscript/reference/iactivescript-getscriptdispatch.md)   
 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)   
 [IActiveScriptParse::ParseScriptText](../../winscript/reference/iactivescriptparse-parsescripttext.md)   
 [IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md)