---
title: IDebugApplication::RemoveStackFrameSniffer | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugApplication.RemoveStackFrameSniffer
apilocation: pdm.dll
helpviewer_keywords: IDebugApplication::RemoveStackFrameSniffer
ms.assetid: 00304b88-e435-4b87-a331-44e7492eb32d
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 11289972dbd39d2e6221fb223a0d933ed90589c2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationremovestackframesniffer"></a>IDebugApplication::RemoveStackFrameSniffer
이 응용 프로그램에서 스택 프레임 열거자 공급자를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT RemoveStackFrameSniffer(  
   DWORD  dwCookie  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwCookie`  
 [in] 반환 된 쿠키는 `AddStackFrameSniffer` 스택 프레임 열거자 공급자가 추가 될 때 메서드.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 `RemoveStackFrameSniffer` 메서드는이 응용 프로그램에서 스택 프레임 열거자 공급자를 제거 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication::AddStackFrameSniffer](../../winscript/reference/idebugapplication-addstackframesniffer.md)   
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IDebugStackFrameSniffer 인터페이스](../../winscript/reference/idebugstackframesniffer-interface.md)