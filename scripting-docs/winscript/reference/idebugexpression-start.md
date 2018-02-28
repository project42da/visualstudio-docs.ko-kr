---
title: IDebugExpression::Start | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugExpression.Start
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpression::Start
ms.assetid: a7af3470-62b5-40f0-987d-63b6b22538b3
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 14d293649e3a6a87c7f594e244378dc2a7e15ac6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugexpressionstart"></a>IDebugExpression::Start
식의 평가 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Start(  
   IDebugExpressionCallBack*  pdecb  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdecb`  
 [in] 식 계산 완료 되었음을 알리는 대 한 콜백. 이 매개 변수가 `NULL`, 이벤트가 발생 하지 않습니다 및 클라이언트를 사용 하 여 식 상태를 폴링해야 `QueryIsComplete`합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 식의 평가 시작합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExpression::Abort](../../winscript/reference/idebugexpression-abort.md)   
 [IDebugExpression 인터페이스](../../winscript/reference/idebugexpression-interface.md)