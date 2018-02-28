---
title: IEnumDebugCodeContexts::Skip | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IEnumDebugCodeContexts.Skip
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugCodeContexts::Skip
ms.assetid: ba917f57-f7a9-419f-96d6-8f4378b12c57
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d053fdfe079636755acf125f5a2c02f8690b2a53
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ienumdebugcodecontextsskip"></a>IEnumDebugCodeContexts::Skip
열거형 시퀀스에 있는 세그먼트의 지정 된 수를 건너뜁니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Skip(  
   ULONG  celt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 열거형 시퀀스를 건너뛰려면에서 세그먼트의 수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 지정 된 열거 순서에서 세그먼트 수를 건너뜁니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugCodeContexts 인터페이스](../../winscript/reference/ienumdebugcodecontexts-interface.md)