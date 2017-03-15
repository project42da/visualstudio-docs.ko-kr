---
title: "IDebugExpressionEvaluator3 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugExpressionEvaluator3 인터페이스"
ms.assetid: c27c2a14-300b-4535-be22-767c83602f69
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugExpressionEvaluator3
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 향상 된 파서 트리 식 계산기를 \(EE\)를 나타냅니다.  
  
## 구문  
  
```  
IDebugExpressionEvaluator3 : IDebugExpressionEvaluator2  
```  
  
## 호출자에 대 한 참고 사항  
 이 버전의 파서에서 기호 공급자 및 평가 프레임의 주소를 전달합니다.  
  
## 메서드  
 메서드 외에 [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md) 인터페이스를이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[Parse2](../../../extensibility/debugger/reference/idebugexpressionevaluator3-parse2.md)|기호 공급자 및 평가 프레임의 주소를 제공 하는 구문 분석 된 식에는 식 문자열을 변환 합니다.|  
  
## 요구 사항  
 헤더: Ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll