---
title: "식 계산기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "식 [디버깅 SDK]"
  - "디버깅 [디버깅 SDK], 식 계산"
  - "식 계산"
ms.assetid: f9381b2f-99aa-426c-aea0-d9c15f3c859b
caps.latest.revision: 19
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 19
---
# 식 계산기
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

식 계산기 \(EE\) IDE 중단 모드에 있을 때 사용자가 볼 수 있도록 구문을 구문 분석 하 고 런타임 시, 변수 및 식을 평가 하는 언어를 검토 합니다.  
  
## 식 계산기를 사용 하 여  
 식을 사용 하 여 만들는 [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 메서드 같이:  
  
1.  디버그 엔진 \(DE\) 구현 하는 [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스입니다.  
  
2.  디버그 패키지를 가져옵니다는 `IDebugExpressionContext2` 에서 개체는 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) 인터페이스와 호출의 `IDebugStackFrame2::ParseText` 메서드를 가져올 수는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 개체입니다.  
  
3.  디버그 패키지 호출을 [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 메서드 또는 [EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 식의 값을 가져오는 방법을.  `IDebugExpression2::EvaluateAsync`명령\/직접 실행 창에서 호출 됩니다.  다른 모든 UI 구성 요소를 호출 `IDebugExpression2::EvaluateSync`.  
  
4.  식 계산 결과로 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 이름, 형식 및 값은 식 계산의 결과 포함 하는 개체입니다.  
  
 식 계산 중 EE 기호 공급자 구성 요소에서 정보를 필요로합니다.  기호 공급자 식별 하 고 구문 분석 된 식을 이해 하는 데 사용 하는 기호화 된 정보를 제공 합니다.  
  
 비동기 식은 실행이 완료 되 면 비동기 이벤트 여 DE 세션 디버그 매니저 \(SDM\)을 통해 IDE 식 계산이 완료 되었음을 알리기 위해 보내집니다.  동기 식 계산이 완료 되 면 평가 결과 호출에서 반환 됩니다는 `IDebugExpression2::EvaluateSync` 메서드가 있습니다.  
  
## 구현 참고 사항  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅 엔진 예상 공용 언어 런타임 \(CLR\) 인터페이스를 사용 하 여 식 계산기와 대화할 수 있습니다.  따라서 식 계산기는 작동에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] CLR 디버깅 엔진을 지원 합니다 \(일부 debugref.doc에서 모든 CLR 디버깅 인터페이스의 전체 목록을 찾을 수 있습니다의 [!INCLUDE[winsdklong](../../deployment/includes/winsdklong_md.md)]\).  
  
## 참고 항목  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)