---
title: IDebugApplicationThread110::IsSuspendedForBreakPoint | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread110::IsSuspendedForBreakPoint
ms.assetid: 60688222-557f-4a43-a19b-846cee393cd0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 377eb51d2cdccd021d04bc1bbfaf2f9ea009624d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationthread110issuspendedforbreakpoint"></a>IDebugApplicationThread110::IsSuspendedForBreakPoint
결정 여부 [IDebugApplicationThreadEvents110::OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md) 이 스레드에서 호출 되었고 완료 되지 않았습니다.  
  
> [!IMPORTANT]
>  [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md) 구현 PDM v11.0 이상에 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsSuspendedForBreakPoint([out, annotation("_Out_")] BOOL * pfIsSuspended);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfIsSuspended`  
 [out] `true` 경우는 스레드가 일시 중단 되는 중단점에 대 한 그렇지 않으면 `false`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md)