---
title: "중단점 오류 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- breakpoints, errors
- debugging [Debugging SDK], breakpoint errors
- errors [Debugging SDK]
ms.assetid: 79221c6b-a924-4c8e-a778-e312e4e0c0c8
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f9c197bbaf8fb79ea4396c7b2e36af94d59c7ea8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="breakpoint-errors"></a>중단점 오류
다음 코드에 중단점을 바인딩하려는 경우에 프로세스를 설명 하지만 실패 합니다.  
  
## <a name="troubleshooting-a-breakpoint-error"></a>중단점 오류 문제 해결  
  
1.  디버그 엔진 (DE) 보냅니다는 [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) 세션 디버그 관리자 (SDM)에 있습니다.  
  
2.  SDM 호출 [IDebugBreakpointErrorEvent2::GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md) (IDebugErrorBreakpoint2 * * `ppErrorBP`) 오류 중단점을 얻으려고 합니다.  
  
3.  SDM 호출 [IDebugErrorBreakpoint2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md) 오류 중단점의 원본이 되는 보류 중인 중단점을 얻으려고 합니다.  
  
4.  SDM 호출 [IDebugErrorBreakpoint2::GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) 오류 중단점을 바인딩하지 못했습니다 하는 이유는 이유를 얻으려고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 이벤트 호출](../../extensibility/debugger/calling-debugger-events.md)