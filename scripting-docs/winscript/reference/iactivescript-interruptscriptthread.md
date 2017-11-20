---
title: IActiveScript::InterruptScriptThread | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScript.InterruptScriptThread
apilocation: scrobj.dll
helpviewer_keywords: IActiveScript_InterruptScriptThread
ms.assetid: 2304d035-6d39-4811-acd3-8a9640fdbef6
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ad717ee950dda4f0f0d7a14292f0f5f150ab4973
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptinterruptscriptthread"></a>IActiveScript::InterruptScriptThread
(이벤트 싱크는 즉시 실행 또는 매크로 호출) 실행 중인 스크립트 스레드 실행을 중단합니다. 걸려 (예를 들어 무한 루프) 하는 스크립트를 종료 하려면이 메서드를 사용할 수 있습니다. 호스트 개체 또는 비 기반 설명선 발생 하지 아닌 스레드에서 호출할 수 있습니다는 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT InterruptScriptThread(  
    SCRIPTTHREADID   stidThread,  // identifier of thread  
    const EXCEPINFO *pexcepinfo,  // receives error information  
    DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stidThread`  
 [in] 인터럽트 또는 다음과 같은 특수 스레드 식별자 값 중 하나에는 스레드의 식별자:  
  
|값|의미|  
|-----------|-------------|  
|SCRIPTTHREADID_ALL|모든 스레드가 있습니다. 인터럽트 현재 진행 중인 모든 스크립트 메서드에 적용 됩니다. 호출자에서 스크립트 끊길을 요청 하지 않으면 다음 스크립트를 사용한 이벤트 하면 스크립트 코드를 호출 하 여 다시 실행은 [IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md) 는 SCRIPTSTATE_DISCONNECTED 사용 하 여 메서드 또는 SCRIPTSTATE_INITIALIZED 플래그를 설정합니다.|  
|SCRIPTTHREADID_BASE|기본 스레드입니다. 즉,는 스크립팅 엔진 스레드 인스턴스화 되었습니다.|  
|SCRIPTTHREADID_CURRENT|현재 실행 중인 스레드입니다.|  
  
 `pexcepinfo`  
 [in] 주소는 `EXCEPINFO` 중단 된 스크립트에 보고 해야 하는 오류 정보가 포함 된 구조입니다.  
  
 `dwFlags`  
 [in] 중단과 관련 된 옵션 플래그입니다. 다음 값 중 하나일 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|SCRIPTINTERRUPT_DEBUG|지원, 현재 스크립트 실행 위치에서 스크립팅 엔진 디버거를 입력 합니다.|  
|SCRIPTINTERRUPT_RAISEEXCEPTION|스크립팅 엔진의 언어에서 지 원하는, 예외를 처리 하는 스크립트를 사용 합니다. 그렇지 않으면 스크립트 메서드가 중단 되 고 호출자에 오류 코드가 반환 됩니다. 즉, 이벤트 원본 또는 매크로 호출자는 합니다.|  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_INVALIDARG`|인수가 올바르지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진에 로드 되거나 않은 초기화).|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)