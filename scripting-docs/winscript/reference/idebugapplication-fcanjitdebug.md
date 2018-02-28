---
title: IDebugApplication::FCanJitDebug | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugApplication.FCanJitDebug
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::FCanJitDebug
ms.assetid: d7ddac65-4864-411f-bf66-34a46c03f239
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8ca6b990011252bde581168a272da1041dc24f41
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationfcanjitdebug"></a>IDebugApplication::FCanJitDebug
적시에 (JIT) 디버거에 등록 되어 있는지 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
BOOL FCanJitDebug();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수가 없습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 반환 하는 메서드가 성공 했으며 JIT 디버거가 등록을 `TRUE`합니다. 그 외의 경우 `FALSE`를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 JIT 디버거가 등록 되어 있는지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)