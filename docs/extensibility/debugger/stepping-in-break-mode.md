---
title: "중단 모드에서 단계별 실행 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- break mode, stepping
- stepping, in break mode
- debugging [Debugging SDK], stepping in break mode
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 011de9ce3e4e1445354f907dcf56a0f4ecbef6bc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="stepping-in-break-mode"></a>중단 모드에서 단계별 실행
다음은 디버거가 중단 모드에 있는 코드를 단계별로 실행 해야 하는 경우 발생 하는 프로세스에 대 한 설명입니다.  
  
## <a name="stepping-process"></a>단계별 실행 프로세스  
  
1.  호출 [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md) 와 [STEPKIND](../../extensibility/debugger/reference/stepkind.md) 및 [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) 단계를 실행 하는 인수입니다.  
  
2.  단계가 완료 되 면 보내기는 [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) stopping 이벤트로 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)