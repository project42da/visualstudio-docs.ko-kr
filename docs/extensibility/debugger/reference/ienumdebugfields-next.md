---
title: IEnumDebugFields::Next | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugFields::Next
helpviewer_keywords: IEnumDebugFields::Next method
ms.assetid: 22c177a2-af81-4234-812b-f9b47be245a2
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fc9776314264d1f1e6fec2b33dcf8aea2286f894
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugfieldsnext"></a>IEnumDebugFields::Next
이 메서드는 열거형에서 다음 요소 집합을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Next(  
   ULONG         celt,  
   IDebugField** rgelt,  
   ULONG*        pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint          celt,  
   IDebugField[] rgelt,  
   ref uint      pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 검색할 요소의 수입니다. 또한의 최대 크기를 지정 된 `rgelt` 배열입니다.  
  
 `rgelt`  
 [out에서] 배열 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 요소를 채워야 합니다.  
  
 `pceltFetched`  
 [out] 에 실제로 반환 된 요소의 수를 반환 `rgelt`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 요소 요청 된 수보다 적은지 반환 될 수 있습니다; 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)