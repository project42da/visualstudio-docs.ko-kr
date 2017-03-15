---
title: "IDebugExpressionEvaluationCompleteEvent2::GetResult | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExpressionEvaluationCompleteEvent2::GetResult"
helpviewer_keywords: 
  - "IDebugExpressionEvaluationCompleteEvent2::GetResult"
ms.assetid: d9ad3e22-b6b2-421e-9a43-6bb8c70d12a9
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugExpressionEvaluationCompleteEvent2::GetResult
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

식 계산의 결과를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetResult(   
   IDebugProperty2** ppResult  
);  
```  
  
```c#  
int GetResult(   
   out IDebugProperty2 ppResult  
);  
```  
  
#### 매개 변수  
 `ppResult`  
 \[out\] 반환 된 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 식 계산의 결과 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 반환 되는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 개체는 계산된 된 식의 값을 포함 합니다.  이 값 배열 등 복잡 한 값을 사용할 수 있지만 사용자에 게 표시 되는 값 문자열 이거나 숫자는 되어야 최종 결과 note입니다.  
  
## 참고 항목  
 [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)