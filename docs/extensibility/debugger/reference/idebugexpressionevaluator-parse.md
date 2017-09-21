---
title: "IDebugExpressionEvaluator::Parse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExpressionEvaluator::Parse"
helpviewer_keywords: 
  - "IDebugExpressionEvaluator::Parse 메서드"
ms.assetid: e6e31b3a-63a7-4293-bcda-267eb78dffb6
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugExpressionEvaluator::Parse
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 구문 분석 된 식을 식 문자열을 변환합니다.  
  
## 구문  
  
```cpp#  
HRESULT Parse(   
   LPCOLESTR                upstrExpression,  
   PARSEFLAGS               dwFlags,  
   UINT                     nRadix,  
   BSTR*                    pbstrError,  
   UINT*                    pichError,  
   IDebugParsedExpression** ppParsedExpression  
);  
```  
  
```c#  
int Parse(  
   string                     upstrExpression,   
   enum_PARSEFLAGS            dwFlags,   
   uint                       nRadix,   
   out string                 pbstrError,   
   out uint                   pichError,   
   out IDebugParsedExpression ppParsedExpression  
);  
```  
  
#### 매개 변수  
 `upstrExpression`  
 \[in\] 구문 분석할 식 문자열입니다.  
  
 `dwFlags`  
 \[in\] 컬렉션의 [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md) 식 구문 분석할 방식을 결정 하는 상수입니다.  
  
 `nRadix`  
 \[in\] 임의의 숫자 정보를 해석 하는 데 사용할 기 수입니다.  
  
 `pbstrError`  
 \[out\] 사람이 읽을 수 있는 텍스트 형식으로 오류를 반환합니다.  
  
 `pichError`  
 \[out\] 시작 오류 문자 식 문자열을 반환합니다.  
  
 `ppParsedExpression`  
 \[out\] 구문 분석 된 식의 반환은 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 구문 분석 된 식을 실제 값을 생성합니다.  구문 분석 된 식을 반환 계산 될 준비가 됩니다.  
  
## 참고 항목  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)   
 [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md)