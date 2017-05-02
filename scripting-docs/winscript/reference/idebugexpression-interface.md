---
title: "IDebugExpression 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugExpression 인터페이스"
ms.assetid: 36c00ffb-7160-4c30-a2c9-c9d70c8213cd
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugExpression 인터페이스
비동기적으로 계산된 된 식을 나타냅니다.  스크립트 엔진은 일반적으로이 인터페이스를 구현 합니다.  일반적으로 IDE 디버거는 직접 실행 창의 조사식 창을이 인터페이스를 사용 합니다.  
  
> [!NOTE]
>  `IDebugExpression` 인터페이스는 스택 프레임을 사용할 수 있습니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugExpression` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugExpression::Start](../../winscript/reference/idebugexpression-start.md)|식의 평가 시작합니다.|  
|[IDebugExpression::Abort](../../winscript/reference/idebugexpression-abort.md)|식을 중단합니다.|  
|[IDebugExpression::QueryIsComplete](../../winscript/reference/idebugexpression-queryiscomplete.md)|작업이 완료 되었는지 확인 합니다.|  
|[IDebugExpression::GetResultAsString](../../winscript/reference/idebugexpression-getresultasstring.md)|문자열 작업의 반환 값으로 식이 평가의 결과 반환합니다.|  
|[IDebugExpression::GetResultAsDebugProperty](../../winscript/reference/idebugexpression-getresultasdebugproperty.md)|디버그 속성 및 작업의 반환 값으로 식이 평가의 결과 반환합니다.|