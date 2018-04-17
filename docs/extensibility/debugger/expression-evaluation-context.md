---
title: 식 계산 컨텍스트 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expression evaluation, context
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d1fade5bb18e59a1b9b9e2655ce01b0b5559484e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="expression-evaluation-context"></a>식 계산 컨텍스트
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 을 디버깅 하는 **식 평가 컨텍스트**:  
  
-   식 계산에 대 한 컨텍스트를 나타냅니다. 일반적으로 평가 컨텍스트 변수, 매개 변수, 함수 및 메서드를 평가 하는 어휘 범위에 해당 합니다. 예를 들어 식 평가 컨텍스트에 연결 된 스택 프레임을 해당 하는 경우 지역 변수, 메서드 매개 변수 및 클래스 멤버를 평가 하기 위한 컨텍스트를 제공 합니다.  
  
-   프로그램이 중단점에서 중지 될 때 존재 합니다. 식 자체에 바인딩 및 지정된 된 컨텍스트 내에서 평가 대 한 사용할 준비가 되어 구문 분석 된 식을 나타내는 데이터 구조입니다.  
  
     좀 더 자세하게에서 식이 사용 하 여 작성 되며는 [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) 메서드. 식이 계산 되는 이름 및 유형의 변수 또는 인수 및 값을 포함 하는 인쇄 가능한 문자열을 생성 됩니다. 이 문자열은 조사식 창 또는 IDE의 지역 창에 표시 됩니다.  
  
     지정 된는 `BSTR` 및 [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스 디버그 엔진 (DE)를 만들 수는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 식을 구문 분석 하 여 인터페이스입니다. 지정 된 프로그램 `IDebugExpression2` 인터페이스는 DE 동기 또는 비동기 식 평가 통해 값을 가져올 수 있습니다. 이름 및 유형의 변수 또는 인수를 함께이 값 표시에 대 한 IDE에 전송 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [식 평가 인터페이스](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)