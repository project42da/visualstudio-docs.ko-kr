---
title: IDebugExpressionCallBack::onComplete | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugExpressionCallBack.onComplete
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugExpressionCallBack::onComplete
ms.assetid: d0b89db3-38e7-44e0-93fe-60205f9149dd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa3d7d6173161407619174607eae221e4513cbcd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugexpressioncallbackoncomplete"></a>IDebugExpressionCallBack::onComplete
식 계산 완료 되었음을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT onComplete();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수가 없습니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 식 계산 완료 되 면 호출 됩니다. `IDebugExpression::GetResultAsString` 이 이벤트 처리기 내에서 메서드를 호출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExpressionCallBack 인터페이스](../../winscript/reference/idebugexpressioncallback-interface.md)   
 [IDebugExpression::GetResultAsString](../../winscript/reference/idebugexpression-getresultasstring.md)