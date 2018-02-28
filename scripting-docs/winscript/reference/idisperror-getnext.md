---
title: IDispError::GetNext | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDispError.GetNext
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetNext
ms.assetid: 3e5267f8-ba62-41c3-bd3e-eced2ad85e8e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5cbe4b044f2d3fb1d8ffb08565fc4093fbbe3ec7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idisperrorgetnext"></a>IDispError::GetNext
다음 검색 `IDispError` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetNext(  
   IDispError**  ppde  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppde`  
 [out] 그런 다음 지정 `IDispError` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 다음 검색 `IDispError` 개체입니다. 마지막 이것이 `IDispError` 개체를이 메서드는 NULL을 반환 합니다.  
  
> [!NOTE]
>  이 메서드가 구현되지 않았습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDispError 인터페이스](../../winscript/reference/idisperror-interface.md)