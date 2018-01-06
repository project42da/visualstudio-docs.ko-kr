---
title: "식 평가 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: expression evaluation, interfaces
ms.assetid: 2d259f60-2cd7-460e-b02d-24a8fb202850
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a5ce9f82e88c6275000c17d40e2b1e1494683715
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="expression-evaluation-interfaces"></a>식 평가 인터페이스
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 다음은에 대 한 식 평가 인터페이스는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] Debugging SDK입니다.  
  
## <a name="discussion"></a>토론  
 이러한 인터페이스는 중단 모드에 있는 동안 호출 스택에 포함 된 식을 평가 하는 데 사용 됩니다. 공용 언어 런타임 식 계산기 (EE)에 대해서만 구현 됩니다.  
  
 테이블의 각 인터페이스에서는 다음 목록에서 구현할 수 있는 구성 요소를 보여 줍니다.  
  
-   디버그 엔진 (DE)  
  
-   식 계산기 (EE)  
  
-   Visual Studio (VS)  
  
|인터페이스|에 의해 구현|설명|  
|---------------|--------------------|-----------------|  
|[IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)|EE|변수에 대 한 숫자 별칭을 나타냅니다.|  
|[IDebugAlias2](../../../extensibility/debugger/reference/idebugalias2.md)|EE|숫자 변수, 별칭을 나타내며 식 계산기는 별칭에 대 한 응용 프로그램 도메인을 가져오려면 (EE) 수 있습니다.|  
|[IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)|EE|배열 개체를 나타냅니다.|  
|[IDebugArrayObject2](../../../extensibility/debugger/reference/idebugarrayobject2.md)|EE|관리 되는 배열 개체를 나타내며 (EE) 배열에 대 한 기본 인덱스 (하위 범위)를 결정 하는 식 계산기를 허용 합니다.|  
|[IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)|DE|바인딩 디버그 메모리에서 실제 주소에는 기호는 바인더를 나타냅니다.|  
|[IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)|DE|와 동일는 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) 하지만 인터페이스 형식, 별칭 및 사용자 지정 시각화 도우미에 액세스를 제공 합니다.|  
|[IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)|EE|식 계산기를 나타냅니다.|  
|[IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)|EE|식 계산기 (EE)의 향상 된 버전을 나타냅니다.|  
|[IDebugExpressionEvaluator3](../../../extensibility/debugger/reference/idebugexpressionevaluator3.md)|EE|향상 된 파서 트리는 식 계산기를 (EE)를 나타냅니다.|  
|[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)|EE|함수를 나타냅니다.|  
|[IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)|EE|함수를 나타내고 향상 된 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 인터페이스입니다.|  
|[IDebugIDECallback](../../../extensibility/debugger/reference/idebugidecallback.md)|DE|디버거의 출력 창에 메시지를 표시 하는 식 계산기를 (EE) 수 있습니다.|  
|[IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)|EE|관리 코드 개체를 나타냅니다.|  
|[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)|EE|모든 기호를 나타내는 기본 인터페이스는 메모리 주소에 바인딩됩니다.|  
|[IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)|EE|와 동일는 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 인터페이스 하지만 추가 정보에 대 한 액세스를 제공 합니다.|  
|[IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)|EE|평가 준비가 된 구문 분석 된 식을 나타냅니다.|  
|[IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)|EE|포인터를 나타냅니다.|  
|[IDebugPointerObject3](../../../extensibility/debugger/reference/idebugpointerobject3.md)|EE|구문 분석 트리의 포인터를 나타내며 확장는 **IDebugPointerObject** 인터페이스입니다.|  
|[IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)|EE|형식 시각화 도우미를 통해 한 형식의 값을 수정 하는 기능을 제공 합니다.|  
|[IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)|VS|사용자 지정 뷰어 및 형식 시각화 도우미에 대 한 액세스를 제공합니다.|  
|[IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)|VS|만드는 기능을 제공 된 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) 개체입니다.|  
|[IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)|EE|컬렉션을 나타냅니다 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [API 참조](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)   
 [CLR 식 계산기를 작성합니다.](../../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [형식 시각화 도우미 및 사용자 지정 뷰어](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)