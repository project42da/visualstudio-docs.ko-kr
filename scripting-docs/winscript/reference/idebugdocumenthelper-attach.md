---
title: IDebugDocumentHelper::Attach | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugDocumentHelper.Attach
apilocation: pdm.dll
helpviewer_keywords: IDebugDocumentHelper::Attach
ms.assetid: 834f23a9-716d-44df-b23c-d1bf6da60e79
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97ddb49f61e9df4044eb6e16b853e6cf8155162a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenthelperattach"></a>IDebugDocumentHelper::Attach
이 문서는 문서 트리에서 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Attach(  
   IDebugDocumentHelper*  pddhParent  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pddhParent`  
 [in] 이 문서를 추가할는 문서 트리에서 합니다. NULL이 될 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 문서에이 문서를 추가 합니다. 트리를 사용 하 여 `pddhParent` 부모로 합니다. 경우는 `pddhParent` 은 `NULL`,이 문서에는 최상위 문서 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentHelper::Detach](../../winscript/reference/idebugdocumenthelper-detach.md)   
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)