---
title: "중단점을 삭제 하면 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- breakpoints, deleting
- debugging [Debugging SDK], deleting breakpoints
ms.assetid: 75a046cc-d20a-4c79-ad2d-1f18426ac5d0
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1667da0798bba298fdead26105178905c0b9a9e4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="deleting-a-breakpoint"></a>중단점 삭제
다음 프로세스 보류 중단점을 삭제할 때 설명.  
  
## <a name="deletion-process"></a>삭제 프로세스  
 세션 디버그 관리자 (SDM) 호출 하면 중지는 [IDebugPendingBreakpoint2::Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md) 여기에서 바인딩된 보류 중인 중단점 및 바인딩된 모든 중단점을 제거 하는 메서드입니다.  
  
> [!NOTE]
>  호출 하 여 단일 바인딩된 중단점을 삭제할 수도 있습니다 [IDebugBoundBreakpoint2::Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)