---
title: "Ijsdebugbreakpoint:: Disable 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJSDebugBreakPoint.Disable
apilocation: jscript9diag.dll
ms.assetid: f6f2889c-c001-4ee5-8e3f-4f36235e4fad
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c53ff133fb07d256d00668e499e5996ac650230f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugbreakpointdisable-method"></a>IJsDebugBreakPoint::Disable 메서드
중단점을 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Disable(void);  
```  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 삭제 된 중단점에 호출 된 경우 E_UNEXPECTED를 반환 합니다. 이미 사용할 수 없는 중단점에 호출 된 경우 S_FALSE를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugBreakPoint 인터페이스](../../winscript/reference/ijsdebugbreakpoint-interface.md)