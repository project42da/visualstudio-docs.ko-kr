---
title: IMachineDebugManagerEvents::onRemoveApplication | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IMachineDebugManagerEvents.onRemoveApplication
apilocation: scrobj.dll
helpviewer_keywords: IMachineDebugManagerEvents::onRemoveApplication
ms.assetid: 3ba71bd8-fd69-4a41-99c6-c736c416f227
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe727b65c8a74962cf6a88ce4ab36ad975b26231
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="imachinedebugmanagereventsonremoveapplication"></a>IMachineDebugManagerEvents::onRemoveApplication
응용 프로그램 실행에서 제거 될 때 이벤트를 처리 응용 프로그램 목록입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT onRemoveApplication(  
   IRemoteDebugApplication*  pda,  
   DWORD                     dwAppCookie  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pda`  
 [in] 응용 프로그램 실행에서 제거 된 응용 프로그램 목록입니다.  
  
 `dwAppCookie`  
 [in] 응용 프로그램 목록에서 응용 프로그램을 추가할 때 제공 되는 쿠키입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 응용 프로그램 실행에서 제거 되었습니다 나타냅니다 응용 프로그램 목록입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IMachineDebugManagerEvents 인터페이스](../../winscript/reference/imachinedebugmanagerevents-interface.md)   
 [IMachineDebugManagerEvents::onAddApplication](../../winscript/reference/imachinedebugmanagerevents-onaddapplication.md)