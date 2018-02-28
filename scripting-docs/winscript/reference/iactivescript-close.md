---
title: IActiveScript::Close | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScript.Close
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_Close
ms.assetid: cc7dd63b-1d7e-410a-857b-09ea3aade275
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7c90b5d089ea6665060944e0a6f720a43aa1295a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptclose"></a>IActiveScript::Close
스크립트 엔진이를 현재 로드 된 스크립트를 중단 하 고, 해당 상태를 다른 개체를 따라서 닫힌된 상태를 입력 해야 하는 모든 인터페이스 포인터를 해제 합니다. 이벤트 싱크, 즉시 실행된 한 스크립트 텍스트 및 매크로 호출이 이미 진행 중인 상태 변경 하기 전에 완료 됩니다 (사용 하 여 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) 실행 중인 스크립트 스레드가 취소에). 인터페이스는 순환 참조가 문제를 방지 하려면 배포 전에이 메서드를 만드는 호스트에서 호출 되어야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Close(void);  
```  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|값|의미|  
|-----------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진은 이미 closed 상태에서).|  
|`OLESCRIPT_S_PENDING`|메서드가 성공적으로 대기 하지만 상태가 아직 변경 되지 않습니다. 상태 변경, 사이트 경우 다시 호출 하 여 [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) 메서드.|  
|`S_FALSE`|메서드가 성공 했지만 스크립트가 이미 종결 되었습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)