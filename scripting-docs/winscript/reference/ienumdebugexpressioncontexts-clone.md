---
title: IEnumDebugExpressionContexts::Clone | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IEnumDebugExpressionContexts.Clone
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugExpressionContexts::Clone
ms.assetid: c8070ae1-120c-4b5d-bd3d-ae8fca6f9277
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f548bf0872d042a131c743554d6f45ccca0ebe98
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ienumdebugexpressioncontextsclone"></a>IEnumDebugExpressionContexts::Clone
현재 열거자와 동일한 상태를 포함 하는 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Clone(  
   IEnumDebugExpressionContexts**  ppedec  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppedec`  
 [out] 반환 된 `IEnumDebugExpressionContexts` 열거자의 복제본의 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 현재 열거자와 동일한 상태를 포함 하는 열거자를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumDebugExpressionContexts 인터페이스](../../winscript/reference/ienumdebugexpressioncontexts-interface.md)