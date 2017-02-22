---
title: "식 계산기를 구현합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "식 계산기"
  - "디버깅 [디버깅 SDK], 식 계산기"
ms.assetid: e9ada7be-845e-4baa-bf8f-e4890e7ba490
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 식 계산기를 구현합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 식을 평가 하 여 디버그 엔진 \(DE\), 기호 공급자 \(SP\), 바인더 개체 및 식 계산기 \(EE\) 자체는 복잡 한 상호 작용입니다. 이러한 네 가지 구성 요소는 한 구성 요소에서 구현 되 고 다른에서 사용 하는 인터페이스를 통해 연결 됩니다.  
  
 EE는 문자열의 형태로 DE에서 식을 사용 하 고 구문 분석 하거나 계산. EE는는 DE에서 사용 하는 다음 인터페이스를 구현 합니다.  
  
-   [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)  
  
-   [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md)  
  
 EE 기호 및 개체의 값을 가져오는 DE, 제공한 바인더 개체를 호출 합니다. EE는 DE에 의해 구현 되는 다음 인터페이스를 사용 합니다.  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
-   [IDebugArrayObject](../../extensibility/debugger/reference/idebugarrayobject.md)  
  
-   [IDebugFunctionObject](../../extensibility/debugger/reference/idebugfunctionobject.md)  
  
-   [IDebugPointerObject](../../extensibility/debugger/reference/idebugpointerobject.md)  
  
-   [IDebugManagedObject](../../extensibility/debugger/reference/idebugmanagedobject.md)  
  
-   [IEnumDebugObjects](../../extensibility/debugger/reference/ienumdebugobjects.md)  
  
-   [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)  
  
 EE 구현 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)합니다.`IDebugProperty2` 같은 지역 변수, 기본 형식, 또는 다음에 적절 한 정보를 표시 하는 Visual Studio에는 개체는 식 계산의 결과 설명 하기 위한 메커니즘을 제공 된 **지역**, **조사식**, 또는 **직접 실행** 창입니다.  
  
 SP는 정보를 요청 하는 경우는 DE에 의해 EE에 부여 됩니다. SP 주소 및 등의 필드는 다음 인터페이스와 해당 파생 항목에 설명 하는 인터페이스를 구현 합니다.  
  
-   [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)  
  
-   [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)  
  
-   [IDebugField](../../extensibility/debugger/reference/idebugfield.md)  
  
 EE 이러한 인터페이스를 모두 사용합니다.  
  
## 단원 내용  
 [식 계산기 구현 전략](../../extensibility/debugger/expression-evaluator-implementation-strategy.md)  
 식 계산기 \(EE\) 구현 전략에 대해 3 단계 프로세스를 정의합니다.  
  
## 참고 항목  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)