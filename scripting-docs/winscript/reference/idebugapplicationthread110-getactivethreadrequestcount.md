---
title: IDebugApplicationThread110::GetActiveThreadRequestCount | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread110::GetActiveThreadRequestCount
ms.assetid: 025d2072-1d7f-4448-8aa3-38a014313570
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb4d19bb77a4380c3c0a04f7e7808b82ca3f6ae4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationthread110getactivethreadrequestcount"></a>IDebugApplicationThread110::GetActiveThreadRequestCount
현재 처리 중인 하는 메커니즘을 전환 되는 PDM의 스레드에서 스레드 요청 수를 반환 합니다. 이 번호는 일반적으로 0 또는 1입니다. 그러나 수 수 있습니다 한 번의 호출 스레드 처리를 시작 하지만 스레드에서 동기 호출을 트리거합니다 또는 그렇지 않은 경우 스레드를 일시 중단 하 고 다시 처리할 수 있도록 들어오는 호출을 허용 하는 경우 더 높은 수 (예를 들어 여는 [ IRemoteDebugApplicationEvents 인터페이스](../../winscript/reference/iremotedebugapplicationevents-interface.md) 디버거 스레드에서 실행 하는 이벤트).  
  
> [!IMPORTANT]
>  [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md) 구현 PDM v11.0 이상에 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetActiveThreadRequestCount([out, annotation("_Out_")] UINT * puiThreadRequests);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `puiThreadRequests`  
 [out] 스레드 요청의 수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md)