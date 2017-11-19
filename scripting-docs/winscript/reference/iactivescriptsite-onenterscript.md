---
title: IActiveScriptSite::OnEnterScript | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptSite.OnEnterScript
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptSite_OnEnterScript
ms.assetid: 1ed9178c-fe80-41c4-b74d-23b85f9cddbf
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eb4514770faaaad46c8590e6df03488e3d5bc679
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsiteonenterscript"></a>IActiveScriptSite::OnEnterScript
스크립팅 엔진이 스크립트 코드 실행을 시작 했음을 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT OnEnterScript(void);  
```  
  
## <a name="return-value"></a>반환 값  
 성공하는 경우 `S_OK`가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 스크립팅 엔진 스크립팅 엔진에 모든 항목 또는 재진입이에이 메서드를 호출 해야 합니다. 예를 들어 스크립트는 개체를 호출 다음 스크립팅 엔진에서 처리 하는 이벤트를 발생을 스크립팅 엔진 호출 해야 `IActiveScriptSite::OnEnterScript` 전에 이벤트를 실행 하 고 호출 해야 합니다는 [IActiveScriptSite::OnLeaveScript](../../winscript/reference/iactivescriptsite-onleavescript.md) 이벤트를 실행 한 후 하지만 이벤트를 발생 시킨 개체를 반환 하기 전에 메서드. 이 메서드의 호출을 중첩 될 수 있습니다. 이 메서드를 호출할 때마다 해당 호출을 해야 `IActiveScriptSite::OnLeaveScript`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)