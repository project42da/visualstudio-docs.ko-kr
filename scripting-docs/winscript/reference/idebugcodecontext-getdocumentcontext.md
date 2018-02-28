---
title: IDebugCodeContext::GetDocumentContext | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugCodeContext.GetDocumentContext
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugCodeContext::GetDocumentContext
ms.assetid: 9fe17b65-3a8c-4d21-9b66-0e4ff303af72
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 098d57a5ff0ba14b1dd493ad772eee595a10ec9a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugcodecontextgetdocumentcontext"></a>IDebugCodeContext::GetDocumentContext
이 코드 컨텍스트와 연결 된 문서 컨텍스트를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDocumentContext(  
   IDebugDocumentContext**  ppsc  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppsc`  
 [out] 이 코드 컨텍스트와 연결 된 문서 컨텍스트에서 가져왔습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 텍스트 문서에 대 한 문자 위치 범위의 전체 문에 대 한 텍스트를 포함 되어야 합니다. 따라서 디버거를 IDE를 현재 소스 문을 강조 표시할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCodeContext 인터페이스](../../winscript/reference/idebugcodecontext-interface.md)