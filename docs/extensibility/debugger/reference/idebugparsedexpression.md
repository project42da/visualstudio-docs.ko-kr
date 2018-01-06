---
title: IDebugParsedExpression | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugParsedExpression
helpviewer_keywords: IDebugParsedExpression interface
ms.assetid: be6486ed-b070-4898-95b1-58581bcb4447
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e6ccaf11dc94702b29888a83c108908be3f8f354
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugparsedexpression"></a>IDebugParsedExpression
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스는 구문 분석 된 식을 평가 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugParsedExpression : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 식 계산기는 구문 분석 된 식 평가 위해 준비 된 나타내기 위해이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 에 대 한 호출 [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) 이 인터페이스를 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugParsedExpression`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)|구문 분석 된 식을 평가합니다.|  
  
## <a name="remarks"></a>설명  
 호출자에 게 식을 계산 하 고 준비 되 면 호출 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) 반환 하는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 평가의 결과 포함 하 합니다. 두 부분으로 구성 방법을 평가, 평가, 구문 분석된 된 식에 여러 번 계산 될 수 있습니다. 다음 구문 분석, 식 구문 분석 하는 시간이 오래 걸리는 과정을 무시 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구문 분석](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)