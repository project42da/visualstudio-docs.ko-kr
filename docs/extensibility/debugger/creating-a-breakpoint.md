---
title: "중단점을 만듭니다 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- breakpoints, creating
- debugging [Debugging SDK], creating breakpoints
ms.assetid: 6f9f87bb-192e-45e0-9a7a-ffe729e87f7d
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 529c0a018aa48ab4e66fbe1e550b4d2909dc340f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-a-breakpoint"></a>중단점을 만듭니다.
다음 중단점을 만드는 과정을 설명 합니다.  
  
## <a name="methods-in-breakpoint-creation"></a>중단점을 만드는 방법  
 중단점을 바인딩하는 데 필요한 모듈 로드 될 때 세션 디버그 관리자 (SDM)의 다음 메서드를 호출 합니다.  
  
1.  [IDebugPendingBreakpoint2::Enable](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md)  
  
2.  [IDebugPendingBreakpoint2::Virtualize](../../extensibility/debugger/reference/idebugpendingbreakpoint2-virtualize.md)  
  
3.  [IDebugPendingBreakpoint2::CanBind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)  
  
    > [!NOTE]
    >  **CanBind** 사용자 중단점 창에서 중단점을가 하는 경우에 호출 됩니다.  
  
4.  [IDebugPendingBreakpoint2::Bind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)  
  
5.  [IDebugPendingBreakpoint2::EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)