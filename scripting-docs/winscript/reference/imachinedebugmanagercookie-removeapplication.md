---
title: IMachineDebugManagerCookie::RemoveApplication | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IMachineDebugManagerCookie.RemoveApplication
apilocation:
- scrobj.dll
helpviewer_keywords:
- IMachineDebugManagerCookie::RemoveApplication
ms.assetid: af8f4a52-ec5e-48fa-87de-234d5e6528d0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe0849b2f580eac7759db36335823a737a198e55
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="imachinedebugmanagercookieremoveapplication"></a>IMachineDebugManagerCookie::RemoveApplication
실행 되는 응용 프로그램을 제거 응용 프로그램 목록입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RemoveApplication(  
   DWORD  dwDebugAppCookie,  
   DWORD  dwAppCookie  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwDebugAppCookie`  
 [in] 디버그 응용 프로그램을 식별 하는 쿠키입니다.  
  
 `dwAppCookie`  
 [in] 응용 프로그램의 응용 프로그램 목록에 추가 될 때 제공 되는 쿠키입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버그 프로세스 관리자 때마다 `IProcessDebugManager::RemoveApplication` 라고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IMachineDebugManagerCookie::AddApplication](../../winscript/reference/imachinedebugmanagercookie-addapplication.md)   
 [IMachineDebugManagerCookie 인터페이스](../../winscript/reference/imachinedebugmanagercookie-interface.md)   
 [IProcessDebugManager::RemoveApplication](../../winscript/reference/iprocessdebugmanager-removeapplication.md)