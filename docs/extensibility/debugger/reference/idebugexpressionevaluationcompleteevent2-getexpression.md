---
title: IDebugExpressionEvaluationCompleteEvent2::GetExpression | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugExpressionEvaluationCompleteEvent2::GetExpression
helpviewer_keywords: IDebugExpressionEvaluationCompleteEvent2::GetExpression
ms.assetid: faf6b2dd-2afd-4852-b21c-7e8d3130e141
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5c62180fb992183326fe965e77cfdcd9f4e97ddc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugexpressionevaluationcompleteevent2getexpression"></a>IDebugExpressionEvaluationCompleteEvent2::GetExpression
원래 식을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetExpression(   
   IDebugExpression2** ppExpr  
);  
```  
  
```csharp  
int GetExpression(   
   out IDebugExpression2 ppExpr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppExpr`  
 [out] 반환 된 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md) 구문 분석 하는 식을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 호출에서 만든 개체를 반환 하는이 메서드는 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)   
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)