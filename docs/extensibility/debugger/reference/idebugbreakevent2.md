---
title: IDebugBreakEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBreakEvent2
helpviewer_keywords: IDebugBreakEvent2 interface
ms.assetid: 57dfdbc2-4e68-4dbf-9579-006cd6fb1c62
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3b58e0fb18b8f41f16a6cc92e682363ff531d5ec
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbreakevent2"></a>IDebugBreakEvent2
이 인터페이스는 비동기 나누기가 성공적으로 완료 되었습니다 세션 디버그 관리자 (SDM)을 알려 줍니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugBreakEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 프로그램에서 사용자 나누기를 지원 하기 위해이 인터페이스를 구현 합니다. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 해당이 인터페이스와 같은 개체에 대해 인터페이스를 구현 해야 합니다 (은 SDM 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 액세스로는 `IDebugEvent2` 인터페이스).  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 SDM 호출 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) 때 사용자가을 일시 중지 해야 디버깅 중인 프로그램을 요청 합니다. 프로그램이 성공적으로 일시 중지 되었습니다는 DE 보냅니다는 `IDebugBreakEvent2` 이벤트입니다. 이 이벤트를 사용 하 여 보냅니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 은 SDM 디버깅 중인 프로그램에는 연결 된 경우 제공한 콜백 함수입니다.  
  
## <a name="remarks"></a>설명  
 예를 들어 선택할 수 있는 **모두 중단** 명령을 **디버그** 메뉴 무한 루프를 실행 하는 프로그램에서 벗어납니다. SDM 호출 하 여 중지 하도록 프로그램에 지시 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)합니다. DE 보냅니다 `IDebugBreakEvent2` 프로그램을 마지막으로 중지 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)