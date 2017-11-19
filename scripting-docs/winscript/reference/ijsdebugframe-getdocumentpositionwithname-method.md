---
title: "Ijsdebugframe:: Getdocumentpositionwithname 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IJsDebugFrame.GetDocumentPositionWithName
apilocation: jscript9diag.dll
ms.assetid: 1d994714-2c87-4a9e-ae14-a15eec9520c7
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 49afb5903e190280d226a24b22dc389041861c52
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ijsdebugframegetdocumentpositionwithname-method"></a>IJsDebugFrame::GetDocumentPositionWithName 메서드
사용자 수준 문서 내에서이 스택 프레임의 현재 위치를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDocumentPositionWithName(  
   BSTR *pDocumentName,  
   DWORD *pLine,  
   DWORD *pColumn  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pDocumentName`  
 [out] 정적 스크립트, 문서에 대 한 URL입니다. 동적 스크립트에 대 한 스크립트 (예를 들어, eval 코드, 함수 코드 등)의 유형을 포함 하는 이름을 반환 됩니다.  
  
 `pLine`  
 [out] 문서 내의 1부터 시작 줄 위치입니다.  
  
 `pColumn`  
 [out] 문서 내의 1부터 시작 줄 위치입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IJsDebugFrame 인터페이스](../../winscript/reference/ijsdebugframe-interface.md)