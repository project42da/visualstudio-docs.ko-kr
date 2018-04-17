---
title: 중단 모드에서 단계별 실행 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1cf10254ec4642bd6dd671124d4a0600794de6fb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="stepping-in-break-mode"></a>중단 모드에서 단계별 실행
다음은 디버거가 중단 모드에 있는 코드를 단계별로 실행 해야 하는 경우 발생 하는 프로세스에 대 한 설명입니다.  
  
## <a name="stepping-process"></a>단계별 실행 프로세스  
  
1.  호출 [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md) 와 [STEPKIND](../../extensibility/debugger/reference/stepkind.md) 및 [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) 단계를 실행 하는 인수입니다.  
  
2.  단계가 완료 되 면 보내기는 [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) stopping 이벤트로 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)