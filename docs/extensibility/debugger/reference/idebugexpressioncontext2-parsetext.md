---
title: "IDebugExpressionContext2::ParseText | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExpressionContext2::ParseText"
helpviewer_keywords: 
  - "IDebugExpressionContext2::ParseText"
ms.assetid: f58575db-f926-4ac8-83ff-7b3b86ab61e2
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugExpressionContext2::ParseText
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

나중에 평가 대 한 텍스트 형식의 식을 구문 분석합니다.  
  
## 구문  
  
```cpp#  
HRESULT ParseText(   
   LPCOLESTR           pszCode,  
   PARSEFLAGS          dwFlags,  
   UINT                nRadix,  
   IDebugExpression2** ppExpr,  
   BSTR*               pbstrError,  
   UINT*               pichError  
);  
```  
  
```c#  
int ParseText(   
   string                pszCode,  
   enum_PARSEFLAGS       dwFlags,  
   uint                  nRadix,  
   out IDebugExpression2 ppExpr,  
   out string            pbstrError,  
   out uint              pichError  
);  
```  
  
#### 매개 변수  
 `pszCode`  
 \[in\] 구문 분석할 식입니다.  
  
 `dwFlags`  
 \[in\] 플래그의 조합에서 [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md) 구문 분석을 제어 하는 열거형입니다.  
  
 `nRadix`  
 \[in\] 기 수 숫자 정보를 구문 분석에 사용 될 `pszCode`.  
  
 `ppExpr`  
 \[out\] 반환은 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md) 바인딩 및 평가 대 한 준비가 되어 구문 분석 된 식을 나타내는 개체입니다.  
  
 `pbstrError`  
 \[out\] 식에 오류가 포함 되어 있는 경우 오류 메시지를 반환 합니다.  
  
 `pichError`  
 \[out\] 문자 인덱스에서 오류를 반환 합니다. `pszCode` 식에 오류가 포함 되어 있습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드를 호출 하면 디버그 엔진 \(DE\) 식을 구문 분석 하 고 정확성을 검증 해야 합니다.  `pbstrError` 및 `pichError` 매개 변수가 될 수 있습니다 작성 식이 잘못 된 경우.  
  
 Note 구문 분석만 있는 식이 계산 하도록 합니다.  나중에 호출 하는 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 또는 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 메서드는 구문 분석 된 식을 계산 합니다.  
  
## 예제  
 다음 예제에서는 단순에이 메서드를 구현 하는 방법을 보여 줍니다. `CEnvBlock` 를 노출 하는 개체는 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스입니다.  이 예제 식 환경 변수 이름으로 구문 분석 하 고이 변수에서 값을 검색 합니다.  
  
```cpp#  
HRESULT CEnvBlock::ParseText(  
   LPCOLESTR           pszCode,  
   PARSEFLAGS          dwFlags,  
   UINT                nRadix,  
   IDebugExpression2 **ppExpr,  
   BSTR               *pbstrError,  
   UINT               *pichError)  
{  
   HRESULT hr = E_OUTOFMEMORY;    
   // Create an integer variable with a value equal to one plus    
   // twice the length of the passed expression to be parsed.    
   int iAnsiLen      = 2 * (wcslen(pszCode)) + 1;    
   // Allocate a character string of the same length.    
   char *pszAnsiCode = (char *) malloc(iAnsiLen);    
  
   // Check for successful memory allocation.    
   if (pszAnsiCode) {    
      // Map the wide-character pszCode string to the new pszAnsiCode character string.    
      WideCharToMultiByte(CP_ACP, 0, pszCode, -1, pszAnsiCode, iAnsiLen, NULL, NULL);    
      // Check to see if the app can succesfully get the environment variable.    
      if (GetEnv(pszAnsiCode)) {    
  
         // Create and initialize a CExpression object.    
         CComObject<CExpression> *pExpr;    
         CComObject<CExpression>::CreateInstance(&pExpr);    
            pExpr->Init(pszAnsiCode, this, NULL);    
  
         // Assign the pointer to the new object to the passed argument  
         // and AddRef the object.    
         *ppExpr = pExpr;    
         (*ppExpr)->AddRef();    
         hr = S_OK;    
      // If the program cannot succesfully get the environment variable.    
      } else {    
         // Set the errror message and return E_FAIL.    
         *pbstrError = SysAllocString(L"No such environment variable.");    
         hr = E_FAIL;    
      }    
      // Free the local character string.    
      free(pszAnsiCode);    
   }    
   return hr;    
}    
```  
  
## 참고 항목  
 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)   
 [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md)   
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)