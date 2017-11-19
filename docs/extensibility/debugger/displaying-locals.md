---
title: "지역 변수를 표시 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, displaying locals
ms.assetid: 62264cec-845b-4233-aed7-0b038fa79250
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a00d57b8af1c32c2f94334e2930e8f92b166c89b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="displaying-locals"></a>지역 변수를 표시합니다.
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 항상 실행 컨텍스트는 메서드를 포함 하는 메서드에 라고도 또는 현재 메서드 내에서 이루어집니다. 실행이 일시 중지 하는 경우 Visual Studio 디버그 엔진 (DE) 지역 변수의 목록을 가져오려면 및 전체적으로 지역 메서드를 호출 하는 인수를 호출 합니다. 이러한 지역 및의 값을 표시 하는 visual Studio는 **지역** 창.  
  
 지역 변수를 표시 하려면는 DE 호출는 [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) EE에 속하는 메서드에 평가 컨텍스트를, 기호 공급자 (SP), 현재 실행 주소 및 바인더 개체를 제공 합니다. 자세한 내용은 참조 [평가 컨텍스트에](../../extensibility/debugger/evaluation-context.md)합니다. 호출이 성공 하는 경우는 `IDebugExpressionEvaluator::GetMethodProperty` 메서드가 반환 되는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 현재 실행 주소를 포함 하는 메서드를 나타내는 개체입니다.  
  
 DE 호출 [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 가져오려는 [IEnumDebugPropertyInfo2](../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) 만 지역 변수를 반환 하도록 필터링 되 고 목록을 생성 하기 위해 열거 개체 [DEBUG_PROPERTY_INFO](../../extensibility/debugger/reference/debug-property-info.md)구조입니다. 각 구조는 이름, 형식 및 로컬 값을 포함합니다. 형식 및 값 표시에 적합 한 형식 지정 된 문자열으로 저장 됩니다. 이름, 형식 및 값은 일반적으로 함께 표시 한 줄의 고 **지역** 창.  
  
> [!NOTE]
>  **간략 한 조사식** 및 **조사식** 창에서는 변수 이름, 값 및 형식 같은 형식으로도 표시 합니다. 호출 하 여 해당 값을 가져오는 반면 [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 대신 `IDebugProperty2::EnumChildren`합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [로컬 항목의 샘플 구현](../../extensibility/debugger/sample-implementation-of-locals.md)  
 예제를 사용 하 여 지역 변수를 구현 하는 과정을 단계별로 실행 되도록 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [평가 컨텍스트](../../extensibility/debugger/evaluation-context.md)  
 식 계산기 (EE)를 호출 하는 디버그 엔진 (DE) 통과 3 개 인수에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)