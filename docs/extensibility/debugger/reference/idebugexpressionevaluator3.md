---
title: IDebugExpressionEvaluator3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugExpressionEvaluator3 interface
ms.assetid: c27c2a14-300b-4535-be22-767c83602f69
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3980f48063894d2bbde88a5dbe851e75c450b54c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugexpressionevaluator3"></a>IDebugExpressionEvaluator3
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 향상 된 파서 트리는 식 계산기를 (EE)를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugExpressionEvaluator3 : IDebugExpressionEvaluator2  
```  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 버전의 파서는 기호 공급자 및 평가 프레임의 주소를 전달합니다.  
  
## <a name="methods"></a>메서드  
 에 메서드 외에도 [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[Parse2](../../../extensibility/debugger/reference/idebugexpressionevaluator3-parse2.md)|기호 공급자 및 평가 프레임의 주소를 제공 하는 구문 분석 된 식에는 식 문자열을 변환 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll