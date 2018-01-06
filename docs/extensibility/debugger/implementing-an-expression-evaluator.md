---
title: "식 계산기 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expression evaluators
- debugging [Debugging SDK], expression evaluators
ms.assetid: e9ada7be-845e-4baa-bf8f-e4890e7ba490
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9f18e2e131b6baa325bd7e0b65babee4c3679ed8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-an-expression-evaluator"></a>식 계산기 구현
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 식을 평가 하 여 디버그 엔진 (DE), 기호 공급자 (SP), 바인더 개체 및 식 계산기 (EE) 자체는 복잡 한 상호 작용입니다. 이러한 네 가지 구성 요소 인터페이스 한 구성 요소에서 구현 되 고 다른에서 사용 하 여 연결 됩니다.  
  
 EE 형태의 문자열 DE에서 식을 사용 하 고 구문 분석 하거나이 확인 합니다. EE는 DE에서 사용 되는 다음 인터페이스를 구현 합니다.  
  
-   [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)  
  
-   [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md)  
  
 EE DE, 기호 및 개체의 값을 제공한 바인더 개체를 호출 합니다. DE 구현 하는 다음 인터페이스를 사용 하는 EE:  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
-   [IDebugArrayObject](../../extensibility/debugger/reference/idebugarrayobject.md)  
  
-   [IDebugFunctionObject](../../extensibility/debugger/reference/idebugfunctionobject.md)  
  
-   [IDebugPointerObject](../../extensibility/debugger/reference/idebugpointerobject.md)  
  
-   [IDebugManagedObject](../../extensibility/debugger/reference/idebugmanagedobject.md)  
  
-   [IEnumDebugObjects](../../extensibility/debugger/reference/ienumdebugobjects.md)  
  
-   [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)  
  
 EE 구현 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)합니다. `IDebugProperty2`지역 변수, 기본 형식, 또는 다음에 적절 한 정보를 표시 하는 Visual Studio에는 개체가 식 평가의 결과 설명 하기 위한 메커니즘을 제공 된 **지역**,  **조사식**, 또는 **직접 실행** 창.  
  
 SP 정보를 요청 하는 경우에 EE는 DE로 제공 됩니다. SP 주소 및 다음 인터페이스 및 해당 파생 항목 등의 필드에 설명 하는 인터페이스를 구현 합니다.  
  
-   [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)  
  
-   [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)  
  
-   [IDebugField](../../extensibility/debugger/reference/idebugfield.md)  
  
 EE 이러한 인터페이스를 모두 사용합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [식 계산기 구현 전략](../../extensibility/debugger/expression-evaluator-implementation-strategy.md)  
 식 계산기 (EE) 구현 전략에 대 한 3 단계 프로세스를 정의합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)