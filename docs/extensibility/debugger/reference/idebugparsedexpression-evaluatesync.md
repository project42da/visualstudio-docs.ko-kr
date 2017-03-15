---
title: "IDebugParsedExpression::EvaluateSync | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugParsedExpression::EvaluateSync"
helpviewer_keywords: 
  - "IDebugParsedExpression::EvaluateSync 메서드"
ms.assetid: 0ea04cfa-de87-4b6c-897e-4572c1a28942
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugParsedExpression::EvaluateSync
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 구문 분석 된 식을 계산 하 고 선택적으로 결과를 다른 데이터 형식으로 캐스트.  
  
## 구문  
  
```cpp#  
HRESULT EvaluateSync(   
   DWORD                 dwEvalFlags,  
   DWORD                 dwTimeout,  
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   BSTR                  bstrResultType,  
   IDebugProperty2**     ppResult  
);  
```  
  
```c#  
int EvaluateSync(  
   uint                 dwEvalFlags,   
   uint                 dwTimeout,   
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   string               bstrResultType,   
   out IDebugProperty2  ppResult  
);  
```  
  
#### 매개 변수  
 `dwEvalFlags`  
 \[in\] 함께 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 는 식이 평가 되는 방법을 제어 하는 상수입니다.  
  
 `dwTimeout`  
 \[in\] 이 메서드에서 반환 하기 전에 대기할 시간 \(밀리초\), 최대 시간을 지정 합니다.  사용 `INFINITE` 무제한으로 대기 합니다.  
  
 `pSymbolProvider`  
 \[in\] 로 표시 되는 기호 공급자는 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) 인터페이스입니다.  
  
 `pAddress`  
 \[in\] 로 표시 되는 메서드 내에서 현재 실행 위치에 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  
  
 `pBinder`  
 \[in\] 표현 된 바인더는 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) 인터페이스입니다.  
  
 `bstrResultType`  
 \[in\] 결과 형식 캐스팅 해야 합니다.  이 인수는 null 값입니다.  
  
 `ppResult`  
 \[out\] 반환은 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 는 평가 결과 나타내는 인터페이스입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 식 계산 컨텍스트의 지정 된 `pAddress`를 사용 하 여 포함 하는 메서드를 결정 합니다 및 다음 언어 사용 범위를 규칙 기호 식에서의 값을 결정 합니다.  
  
## 참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)