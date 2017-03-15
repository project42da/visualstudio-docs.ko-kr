---
title: "IDebugExpressionContext2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExpressionContext2"
helpviewer_keywords: 
  - "IDebugExpressionContext2 인터페이스"
ms.assetid: 577fdaae-4b2d-4112-9839-ab899535fa6f
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugExpressionContext2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

식 계산에 대 한 컨텍스트를이 인터페이스를 나타냅니다.  
  
## 구문  
  
```  
IDebugExpressionContext2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\)에서 식이 계산 될 수 있는 컨텍스트를 나타내는 데이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출을 [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) 이 반환 인터페이스입니다.  이 인터페이스는 디버깅 중인 프로그램의 일시 중지 된 스택 프레임을 사용할 때에 액세스할 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugExpressionContext2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetName](../../../extensibility/debugger/reference/idebugexpressioncontext2-getname.md)|평가 컨텍스트 이름을 검색합니다.|  
|[ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)|평가 대 한 텍스트를 기준으로 식을 구문 분석합니다.|  
  
## 설명  
 평가 컨텍스트 식 계산을 수행 하는 범위 이름으로 생각할 수 있습니다.  
  
 프로그램이 중단 된 경우 세션 디버그 매니저 \(SDM\) 스택 프레임에서 DE를 얻습니다 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md).  SDM은 다음 호출 [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) 얻을 수 있는 `IDebugExpressionContext2` 인터페이스.  이 호출 하 여 다음에 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 만들 수 있는 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md) 평가 준비는 구문 분석 된 식을 나타내는 인터페이스를 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)   
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)