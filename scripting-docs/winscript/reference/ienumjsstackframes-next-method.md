---
title: "Ienumjsstackframes:: Next 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IEnumJsStackFrames.Next
apilocation: jscript9diag.dll
ms.assetid: efceb3a1-9239-4f55-9cbb-94670679988b
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e2068bd130e7eb03747b89e2ba107019aa1cd458
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ienumjsstackframesnext-method"></a>IEnumJsStackFrames::Next 메서드
지정 된 프레임 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Next(  
   ULONG cFrameCount,  
   JS_NATIVE_FRAME *pFrames,  
   ULONG *pcFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cFrameCount`  
 [in] 가져올 프레임 수를 지정 합니다.  
  
 `pFrames`  
 [out] 프레임을 저장할 배열입니다.  
  
 `pcFetched`  
 [out] 프레임 수가 반환 됩니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [IEnumJsStackFrames 인터페이스](../../winscript/reference/ienumjsstackframes-interface.md)