---
title: IDebugExpressionEvaluator::GetMethodLocationProperty | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugExpressionEvaluator::GetMethodLocationProperty
helpviewer_keywords: IDebugExpressionEvaluator::GetMethodLocationProperty method
ms.assetid: 52c42a2e-f144-476b-8bef-442464c8fe8e
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 612cdb579615acb7ca5b4b6a34c0c485683c4fe1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugexpressionevaluatorgetmethodlocationproperty"></a>IDebugExpressionEvaluator::GetMethodLocationProperty
이 메서드를 메서드 위치 및 오프셋 메모리 주소를 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMethodLocationProperty(   
   LPCOLESTR             upstrFullyQualifiedMethodPlusOffset,  
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   IDebugProperty2**     ppProperty  
);  
```  
  
```csharp  
int GetMethodLocationProperty(  
   string               upstrFullyQualifiedMethodPlusOffset,   
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   out IDebugProperty2  ppProperty  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `upstrFullyQualifiedMethodPlusOffset`  
 [in] 문자열로 표현 된 메서드 위치와 오프셋을 합니다.  
  
 `pSymbolProvider`  
 [in] 으로 표시 되는 기호 공급자는 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) 개체입니다.  
  
 `pAddress`  
 [in] 으로 표시 되는 메서드에 들어 있는 주소는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 개체입니다.  
  
 `pBinder`  
 [in] 으로 표시 되는 바인더는 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) 개체입니다.  
  
 `ppProperty`  
 [out] 반환 된 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 메모리 주소를 나타내는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 예를 들어 중단점을 설정 하는 반환 된 주소를 사용할 수 있습니다.  
  
 이름에도 불구 하 고 `upstrFullyQualifiedMethodPlusOffset`,이 매개 변수는 부분적으로 정규화 된 메서드 이름이 전달 될 수 있습니다. 이 경우 선택한 방법은 둘러싸는 한 `pAddress`합니다. 이 매개 변수를 해석 하는 방법을 식 계산기 및 지 원하는 언어의 구현에 따라입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)