---
title: "IDebugExpression 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IDebugExpression interface
ms.assetid: 36c00ffb-7160-4c30-a2c9-c9d70c8213cd
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 39e139e09362fc392d1110e26837c52fd4c642c4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugexpression-interface"></a>IDebugExpression 인터페이스
비동기적으로 평가 된 식을 나타냅니다. 스크립트 엔진은 일반적으로이 인터페이스를 구현 합니다. 일반적으로 디버거 IDE는 즉시 실행 창이 활성화 또는 조사식 창에이 인터페이스를 사용 합니다.  
  
> [!NOTE]
>  `IDebugExpression` 인터페이스는 스택 프레임에만 사용할 수 있습니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDebugExpression` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugExpression::Start](../../winscript/reference/idebugexpression-start.md)|식의 평가 시작합니다.|  
|[IDebugExpression::Abort](../../winscript/reference/idebugexpression-abort.md)|식을 중단합니다.|  
|[IDebugExpression::QueryIsComplete](../../winscript/reference/idebugexpression-queryiscomplete.md)|작업이 완료 되는 경우를 결정 합니다.|  
|[IDebugExpression::GetResultAsString](../../winscript/reference/idebugexpression-getresultasstring.md)|문자열 작업의 반환 값을 식 평가의 결과 반환합니다.|  
|[IDebugExpression::GetResultAsDebugProperty](../../winscript/reference/idebugexpression-getresultasdebugproperty.md)|디버그 속성 및 작업의 반환 값으로 식 평가의 결과 반환합니다.|