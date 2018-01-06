---
title: "중단점 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dfdf86124bdaf9160121b7d93263dc1d60425515
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="hitting-a-breakpoint"></a>중단점
다음 설명 디버그 엔진 (DE)을 실행 하거나 단계별로 실행 하는 동안 중단점에 도달 하면 프로세스.  
  
## <a name="troubleshooting-a-hit-breakpoint"></a>적중 횟수 중단점 문제 해결  
  
1.  DE 보냅니다는 [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) 인터페이스으로 **EVENT_SYNC_STOP**합니다.  
  
2.  세션 디버그 관리자 (SDM) 호출 하면 중지 [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) 적중 된 중단점을 얻으려고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)