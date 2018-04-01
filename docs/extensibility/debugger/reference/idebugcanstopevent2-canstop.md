---
title: IDebugCanStopEvent2::CanStop | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugCanStopEvent2::CanStop
helpviewer_keywords:
- IDebugCanStopEvent2::CanStop
ms.assetid: 7d61adbe-6b3d-41f3-86a1-45d9cc01a7f8
caps.latest.revision: 10
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7c5fe4c0ab03e6f0683fff3d43658fde5bc90bf0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcanstopevent2canstop"></a>IDebugCanStopEvent2::CanStop
현재 코드 위치에서 중지 하거나 계속 실행 여부 (DE) 디버그 엔진에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CanStop (   
   BOOL fCanStop  
);  
```  
  
```csharp  
int CanStop (   
   int fCanStop  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fCanStop`  
 [in] 0이 아닌 (`TRUE`)는 DE 현재 코드 위치에서 중지 해야 하는 경우는 그렇지 않은 경우 0 (`FALSE`).  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 일반적으로이 이벤트의 수신기를 호출는 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md) 는 DE을 중지 하려고 하는 이유를 확인 하 고 호출에서 `IDebugCanStopEvent2::CanStop` 적절 한 응답으로 메서드.  
  
 DE 중지 되 면 중지에 대 한 이유를 설명 하는 이벤트를 보냅니다. 전송 된 사용자 또는 신호 break가 나타내는 두 개의 이벤트는 일반적으로 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) 인터페이스 및 나타내는 중단점 이벤트는 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)   
 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)