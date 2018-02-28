---
title: IDebugDocumentHelper::SetLongName | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugDocumentHelper.SetLongName
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::SetLongName
ms.assetid: b6199e5d-9b54-43a2-9775-214b8d022607
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 153655966f3be59f1d01fd375b8669fb7207e2d7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenthelpersetlongname"></a>IDebugDocumentHelper::SetLongName
문서에 대 한 긴 이름을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetLongName(  
   LPCOLESTR  pszLongName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszLongName`  
 [in] 문서의 긴 이름을 포함 하는 null로 끝나는 문자열.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 문서에 대 한 새 긴 이름을 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)