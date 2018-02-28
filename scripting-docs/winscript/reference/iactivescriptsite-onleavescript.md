---
title: IActiveScriptSite::OnLeaveScript | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptSite.OnLeaveScript
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnLeaveScript
ms.assetid: 79af0e22-fbe3-4fae-8a5f-7af8b857678d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aba20c13dc5568165641c5c7b8e871e0b5e8f322
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsiteonleavescript"></a>IActiveScriptSite::OnLeaveScript
호스트에 알려 스크립팅 엔진 스크립트 코드를 실행할 수 없도록 반환 했습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OnLeaveScript(void);  
```  
  
## <a name="return-value"></a>반환 값  
 성공하는 경우 `S_OK`가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 스크립팅 엔진 스크립팅 엔진을 입력 하는 호출 응용 프로그램에 제어를 반환 하기 전에이 메서드를 호출 해야 합니다. 예를 들어 스크립트는 개체를 호출 후 스크립팅 엔진에서 처리 된 이벤트를 발생 시킬, 스크립팅 엔진 호출 해야 합니다는 [IActiveScriptSite::OnEnterScript](../../winscript/reference/iactivescriptsite-onenterscript.md) 메서드 이벤트를 실행 하기 전에 를호출해야하고`IActiveScriptSite::OnLeaveScript`이벤트를 발생 시킨 개체를 반환 하기 전에 이벤트를 실행 한 후 합니다. 이 메서드의 호출을 중첩 될 수 있습니다. 호출할 때마다 `IActiveScriptSite::OnEnterScript` 이 메서드가 해당 호출 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)