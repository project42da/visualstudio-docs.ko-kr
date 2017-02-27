---
title: "IDebugExpressionEvaluator::GetMethodLocationProperty | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExpressionEvaluator::GetMethodLocationProperty"
helpviewer_keywords: 
  - "IDebugExpressionEvaluator::GetMethodLocationProperty 메서드"
ms.assetid: 52c42a2e-f144-476b-8bef-442464c8fe8e
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugExpressionEvaluator::GetMethodLocationProperty
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 메서드 위치와 오프셋 메모리 주소를 변환합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetMethodLocationProperty(   
   LPCOLESTR             upstrFullyQualifiedMethodPlusOffset,  
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   IDebugProperty2**     ppProperty  
);  
```  
  
```c#  
int GetMethodLocationProperty(  
   string               upstrFullyQualifiedMethodPlusOffset,   
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   out IDebugProperty2  ppProperty  
);  
```  
  
#### 매개 변수  
 `upstrFullyQualifiedMethodPlusOffset`  
 \[in\] 메서드 위치와 오프셋을 문자열 형식으로 표현 됩니다.  
  
 `pSymbolProvider`  
 \[in\] 으로 표시 되는 기호 공급자는 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) 개체입니다.  
  
 `pAddress`  
 \[in\] 으로 표시 되는 메서드 내에서 주소를 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 개체입니다.  
  
 `pBinder`  
 \[in\] 바인더로 표시 되는 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) 개체입니다.  
  
 `ppProperty`  
 \[out\] 반환 된 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 메모리 주소를 표시 하는 인터페이스입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 예를 들어, 중단점을 설정 하려면 반환 된 주소를 사용할 수 있습니다.  
  
 이름에도 불구 하 고 `upstrFullyQualifiedMethodPlusOffset`, 부분적으로 정규화 된 메서드 이름을이 매개 변수를 전달할 수 있습니다.  이 경우 선택된 된 메서드를 포함 하는 것입니다 `pAddress`.  이 매개 변수를 해석 하는 방법을 구현에서 지 원하는 언어 및 식 계산기에 있습니다.  
  
## 참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)