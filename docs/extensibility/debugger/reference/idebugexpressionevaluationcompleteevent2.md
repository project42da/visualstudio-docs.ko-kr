---
title: "IDebugExpressionEvaluationCompleteEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExpressionEvaluationCompleteEvent2"
helpviewer_keywords: 
  - "IDebugExpressionEvaluationCompleteEvent2"
ms.assetid: d538fc19-55bf-4231-9595-eb01e84fd1d8
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugExpressionEvaluationCompleteEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 엔진 \(DE\) 비동기 식 계산이 완료 될 때 세션 디버그 매니저 \(SDM\) 보내집니다.  
  
## 구문  
  
```  
IDebugExpressionEvaluationCompleteEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 이 인터페이스를 호출 하 여 시작한 식 계산 완료 보고서에는 DE 구현 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md).  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 DE를 만들고 식 계산이 완료 되 면 보고 합니다이 이벤트 개체를 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 되는 콜백 함수입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugExpressionEvaluationCompleteEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetExpression](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md)|원래 식을 가져옵니다.|  
|[GetResult](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md)|식 계산의 결과를 가져옵니다.|  
  
## 설명  
 평가 성공 여부는 DE이이 이벤트를 보내야 합니다.  
  
 평가 성공 하지 못한 경우는 `DEBUG_PROPINFO_VALUE` 및 `DEBUG_PROPINFO_ATTRIB` 플래그가 없습니다 설정 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 반환 하는 구조체 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) \(는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 개체 DE에서 생성 되어 반환 되는 `IDebugExpressionEvaluationCompleteEvent2` 평가 실패 한 경우 이벤트\).  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)