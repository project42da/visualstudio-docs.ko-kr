---
title: IActiveScriptWinRTErrorDebug::GetRestrictedErrorString | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IActiveScriptWinRTErrorDebug::GetRestrictedErrorString
ms.assetid: d901e049-fb1b-4101-a04a-1395d657f1cf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ade51ae9852519d6a059193aacbfdde49ae82d19
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptwinrterrordebuggetrestrictederrorstring"></a>IActiveScriptWinRTErrorDebug::GetRestrictedErrorString
사용 가능한 경우 오류 문자열을 제한 하는 Windows 런타임 반환 합니다.  
  
> [!IMPORTANT]
>  [IActiveScriptWinRTErrorDebug 인터페이스](../../winscript/reference/iactivescriptwinrterrordebug-interface.md) 구현 PDM v11.0 이상에 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRestrictedErrorString([out] BSTR * errorString);   
```  
  
#### <a name="parameters"></a>매개 변수  
 `errorString`  
 [out] 제한 된 오류 문자열입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptWinRTErrorDebug 인터페이스](../../winscript/reference/iactivescriptwinrterrordebug-interface.md)