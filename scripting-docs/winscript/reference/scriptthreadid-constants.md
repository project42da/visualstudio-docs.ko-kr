---
title: "SCRIPTTHREADID 상수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: SCRIPTTHREADID
apilocation: scrobj.dll
helpviewer_keywords: SCRIPTTHREADID
ms.assetid: 1df9940c-ad0c-42d8-96b9-6a6abe2382e6
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc692716115ea0c205b1cfd982b189fffd54a9ac
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="scriptthreadid-constants"></a>SCRIPTTHREADID 상수
스레드의 유형을 지정 하는 데 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef DWORD SCRIPTTHREADID;  
```  
  
## <a name="constants"></a>상수  
  
|상수|값|의미|  
|--------------|-----------|-------------|  
|SCRIPTTHREADID_CURRENT|0xFFFFFFFD|현재 실행 중인 스레드입니다.|  
|SCRIPTTHREADID_BASE|0xFFFFFFFE|기본 스레드입니다. 즉,는 스크립팅 엔진 스레드 인스턴스화 되었습니다.|  
|SCRIPTTHREADID_ALL|0xFFFFFFFF|모든 스레드가 있습니다.|  
  
## <a name="remarks"></a>설명  
 `SCRIPTTHREADID` 유형은에 사용 됩니다 `IActiveScript::GetCurrentScriptThreadID`, `IActiveScript::GetScriptThreadID`, `IActiveScript::GetScriptThreadState`, 및 `IActiveScript::InterruptScriptThread`, 상수만 사용할 수 있지만 `IActiveScript::GetScriptThreadState` 및 `IActiveScript::InterruptScriptThread`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScript::GetCurrentScriptThreadID](../../winscript/reference/iactivescript-getcurrentscriptthreadid.md)   
 [IActiveScript::GetScriptThreadID](../../winscript/reference/iactivescript-getscriptthreadid.md)   
 [IActiveScript::GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md)   
 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)