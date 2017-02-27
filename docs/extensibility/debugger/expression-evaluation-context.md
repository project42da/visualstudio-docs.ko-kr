---
title: "식 평가 컨텍스트 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "식 계산, 컨텍스트"
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# 식 평가 컨텍스트
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅은  **식 계산 컨텍스트의**:  
  
-   식 계산에 대 한 컨텍스트를 나타냅니다.  일반적으로, 평가 컨텍스트를 계산할 변수, 매개 변수, 함수 및 메서드 내의 어휘 범위에 해당 합니다.  예를 들어, 스택 프레임과 연결 된 식 평가 컨텍스트 로컬 변수, 메서드 매개 변수 및 클래스 멤버 \(있는 경우\)를 확인 하기 위해 컨텍스트를 제공 합니다.  
  
-   프로그램이 중단점에서 중지 했을 때 존재 합니다.  식 자체 및 지정 된 컨텍스트 내에서 계산에 대 한 준비가 된 구문 분석 된 식을 나타내는 데이터 구조입니다.  
  
     에 자세히를 사용 하 여 식을 생성 됩니다 있는 [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 메서드.  식이 계산 되 면 이름 및 변수 또는 인수와 해당 값의 형식을 포함 하는 인쇄 가능한 문자열을 생성 합니다.  이 문자열에는 조사식 창이 나 지역 창에는 IDE의 표시 됩니다.  
  
     주어는 `BSTR` 및 [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) 디버그 엔진 \(DE\) 인터페이스를 만들 수 있습니다는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 인터페이스는 식을 구문 분석 하 여.  주어는 `IDebugExpression2` 인터페이스, 동기 또는 비동기 식 계산 하는 값은 DE에 얻을 수 있습니다.  이 값은 이름 및 형식 변수 또는 인수를 디스플레이를 IDE로 전송 됩니다.  
  
## 참고 항목  
 [식 평가 인터페이스](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)