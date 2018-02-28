---
title: "SCRIPTSTATE 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- SCRIPTSTATE
apilocation:
- scrobj.dll
helpviewer_keywords:
- SCRIPTSTATE enum
ms.assetid: 5f5deb05-c4bb-4964-8077-e624c6b2a14e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 35e062a9c2f3076144063ffb77895c8a03ecc4ac
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="scriptstate-enumeration"></a>SCRIPTSTATE 열거형
스크립팅 엔진의 상태를 지정 합니다. 이 열거형은에서 사용 된 [IActiveScript::GetScriptState](../../winscript/reference/iactivescript-getscriptstate.md) , [IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md) , 및 [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum tagSCRIPTSTATE {  
    SCRIPTSTATE_UNINITIALIZED = 0,  
    SCRIPTSTATE_INITIALIZED   = 5,  
    SCRIPTSTATE_STARTED       = 1,  
    SCRIPTSTATE_CONNECTED     = 2,  
    SCRIPTSTATE_DISCONNECTED  = 3,  
    SCRIPTSTATE_CLOSED        = 4  
} SCRIPTSTATE;  
```  
  
## <a name="enumeration-values"></a>열거형 값  
  
|||  
|-|-|  
|SCRIPTSTATE_UNINITIALIZED|스크립트에 방금 만든 하지만 아직 초기화 되지 않은 된를 사용 하 여 프로그램 `IPersist*` 인터페이스 및 [IActiveScript::SetScriptSite](../../winscript/reference/iactivescript-setscriptsite.md) 합니다.|  
|SCRIPTSTATE_INITIALIZED|스크립트가 초기화 된 하지만 (다른 개체에 연결 또는 이벤트 싱크)를 실행 또는 코드를 실행 됩니다. 호출 하 여 실행 한 코드를 쿼리할 수는 [IActiveScriptParse::ParseScriptText](../../winscript/reference/iactivescriptparse-parsescripttext.md) 메서드.|  
|SCRIPTSTATE_STARTED|스크립트 코드를 실행할 수 있습니다 하 여 추가 된 개체의 이벤트를 아직 싱크 하지는 않지만 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) 메서드.|  
|SCRIPTSTATE_CONNECTED|스크립트는 로드 되 고 이벤트 싱크를 위해 연결 합니다.|  
|SCRIPTSTATE_DISCONNECTED|스크립트가 로드 되 고 런타임 실행 상태를 사용 하는 하지만 이벤트 싱크에서 일시적으로 연결이 있습니다.|  
|SCRIPTSTATE_CLOSED|스크립트 종료 되었습니다. 스크립트 엔진이 더 이상 작동하지 않고 대부분의 메서드에 대해 오류를 반환합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 상수, 열거형 및 오류 코드](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)