---
title: IDebugApplicationThread110::IsThreadCallable | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread110::IsThreadCallable
ms.assetid: 2a75a366-801d-47e0-bba3-51aa669e03a7
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b34e2c45d7e94c72ade62780f46f4b5c7c22405e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationthread110isthreadcallable"></a>IDebugApplicationThread110::IsThreadCallable
이 스레드는 PDM 스레드 전환 SynchronousCallInThread 같은 메커니즘을 사용 하 여 호출에서 처리 하는 상태 인지 여부를 결정 합니다.  
  
> [!IMPORTANT]
>  [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md) 구현 PDM v11.0 이상에 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsThreadCallable([out, annotation("_Out_")] BOOL * pfIsCallable);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfIsCallable`  
 [out] `true` 스레드가 경우 호출할 수, 그렇지 않으면 `false`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md)