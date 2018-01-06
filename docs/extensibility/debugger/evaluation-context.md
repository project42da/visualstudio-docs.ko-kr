---
title: "평가 컨텍스트에 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, context
ms.assetid: 008a20c7-1b27-4013-bf96-d6a3f510da02
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9a490ef7c4ea42fe85c291ee913d7ad5e1cda1bb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="evaluation-context"></a>평가 컨텍스트
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 식 계산기 (EE)를 호출 하는 디버그 엔진 (DE), 3 개 인수에 전달 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) 다음 표와 같이 찾아서 기호, 평가 대 한 컨텍스트를 결정 합니다.  
  
## <a name="arguments"></a>인수  
  
|인수|설명|  
|--------------|-----------------|  
|`pSymbolProvider`|[IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) 기호를 식별 하는 데 사용할 기호 처리기 (SH)를 지정 하는 인터페이스입니다.|  
|`pAddress`|[IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) 현재 실행 지점을 지정 하는 인터페이스입니다. 실행 중인 코드가 포함 하는 메서드를 찾는 데 사용할 수 있습니다이 있습니다.|  
|`pBinder`|[IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) 값과 이름이 지정 된 기호 형식을 찾는 데 사용할 수 있는 인터페이스입니다.|  
  
 `IDebugParsedExpression::EvaluateSync`반환 된 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 결과 값 및 해당 형식을 나타내는 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [키 식 계산기 인터페이스](../../extensibility/debugger/key-expression-evaluator-interfaces.md)   
 [지역 변수를 표시합니다.](../../extensibility/debugger/displaying-locals.md)   
 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)