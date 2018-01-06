---
title: IDebugParsedExpression::EvaluateSync | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugParsedExpression::EvaluateSync
helpviewer_keywords: IDebugParsedExpression::EvaluateSync method
ms.assetid: 0ea04cfa-de87-4b6c-897e-4572c1a28942
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 261359ae3dc82f8544d0f48cf0e8f1103ccedd5b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugparsedexpressionevaluatesync"></a>IDebugParsedExpression::EvaluateSync
이 메서드는 구문 분석 된 식을 평가 하 고 필요에 따라 다른 데이터 형식으로 결과 캐스팅 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
  
```csharp  
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
  
#### <a name="parameters"></a>매개 변수  
 `dwEvalFlags`  
 [in] 조합을 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 식이 계산 되도록 하는 방법을 제어 하는 상수입니다.  
  
 `dwTimeout`  
 [in] 이 메서드로부터 반환 하기 전에 대기할 밀리초 단위로 최대 시간을 지정 합니다. 사용 하 여 `INFINITE` 무기한 대기를 나타냅니다.  
  
 `pSymbolProvider`  
 [in] 으로 표시 되는 기호 공급자는 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) 인터페이스입니다.  
  
 `pAddress`  
 [in] 으로 표시 되는 메서드 내에서 현재 실행 위치는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  
  
 `pBinder`  
 [in] 으로 표시 되는 바인더는 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) 인터페이스입니다.  
  
 `bstrResultType`  
 [in] 에 형식 결과 캐스팅 해야 합니다. 이 인수는 null 값을 수 있습니다.  
  
 `ppResult`  
 [out] 반환 된 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 평가의 결과 나타내는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 식 계산 컨텍스트를 지정 하 여 `pAddress`, 포함 하는 방법을 결정할 수 있습니다 및 식에 있는 기호의 값을 결정 하려면 다음 규칙 사용 하 여 언어 범위입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)