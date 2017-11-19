---
title: "Ijsdebugbreakpoint:: Getdocumentposition 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJSDebugBreakPoint.GetDocumentPosition
apilocation: jscript9diag.dll
ms.assetid: 886df8ba-a59a-48a7-87f2-3b669e71528f
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c33751b0173626814f042fdc54a7d496b644573
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugbreakpointgetdocumentposition-method"></a>IJsDebugBreakPoint::GetDocumentPosition 메서드
중단점이 바인딩된 문의 위치를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDocumentPosition(  
   UINT64 *pDocumentId,  
   DWORD *pCharacterOffset,  
   DWORD *pStatementCharCount  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pDocumentId`  
 [out] 소스 문서 (포인터는 IDebugDocumentText에)에 대 한 고유 ID입니다.  
  
 `pCharacterOffset`  
 [out] 스크립트의 시작 부분부터 0 기반 문자 오프셋입니다.  
  
 `pStatementCharCount`  
 [out] 시작 된 현재 문의 길이 * pCharacterOffset 문자 수입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugBreakPoint 인터페이스](../../winscript/reference/ijsdebugbreakpoint-interface.md)