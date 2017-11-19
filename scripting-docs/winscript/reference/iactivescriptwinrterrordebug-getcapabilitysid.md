---
title: IActiveScriptWinRTErrorDebug::GetCapabilitySid | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IActiveScriptWinRTErrorDebug::GetCapabilitySid
ms.assetid: 469463d2-5e73-4c53-9ffd-d0ca7460aa5c
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 78d53b498ba88fae50cfaca106a65a2bb07d21a5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptwinrterrordebuggetcapabilitysid"></a>IActiveScriptWinRTErrorDebug::GetCapabilitySid
사용 가능한 경우 Windows 런타임 오류에 대 한 기능 SID를 반환 합니다.  
  
> [!IMPORTANT]
>  [IActiveScriptWinRTErrorDebug 인터페이스](../../winscript/reference/iactivescriptwinrterrordebug-interface.md) 구현 PDM v11.0 이상에 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCapabilitySid([out] BSTR * capabilitySid);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `capabilitySid`  
 기능 오류의 SID입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptWinRTErrorDebug 인터페이스](../../winscript/reference/iactivescriptwinrterrordebug-interface.md)