---
title: IActiveScriptSiteInterruptPoll::QueryContinue | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptSiteInterruptPoll.QueryContinue
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptSiteInterruptPoll::QueryContinue
ms.assetid: 41ac3807-f8b4-4a0e-bcc6-556bc89f3904
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 93323d500ae7e99957c365d60741fa612ba0fc34
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsiteinterruptpollquerycontinue"></a>IActiveScriptSiteInterruptPoll::QueryContinue
호스트를에서 스크립트를 종료 해야를 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT QueryContinue();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수가 없습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|호출에 성공 하 고 호스트를 계속 실행할 스크립트를 허용 합니다.|  
|`S_FALSE`|성공한 호출 하 고 스크립트를 종료 하는 호스트 요청.|  
  
## <a name="remarks"></a>설명  
 호스팅된 스크립트 하지 않으면 종료 해야의 반환 값은 `QueryContinue` 방법은 `S_OK`합니다. 반환 값이 `S_FALSE` 호스트 명시적으로 요청 하는 스크립트가 종료를 나타냅니다.  
  
 다중 스레드는 호스트에서 사용할 수는 `IActiveScript::InterruptScriptThread` 메서드는 스크립트를 종료 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSiteInterruptPoll 인터페이스](../../winscript/reference/iactivescriptsiteinterruptpoll-interface.md)   
 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)