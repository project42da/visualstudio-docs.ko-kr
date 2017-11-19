---
title: EVENTATTRIBUTES | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EVENTATTRIBUTES
helpviewer_keywords: EVENTATTRIBUTES enumeration
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 097a61ff6c96fd4901265ad960169fd5ec7244c2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="eventattributes"></a>EVENTATTRIBUTES
이벤트 특성을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
typedef DWORD EVENTATTRIBUTES;  
```  
  
```csharp  
public enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
```  
  
## <a name="members"></a>멤버  
 EVENT_ASYNCHRONOUS  
 이벤트는 비동기적 이며 필요한 이벤트에 응답을 나타냅니다.  
  
 EVENT_SYNCHRONOUS  
 이 이벤트는 동기적입니다; 나타냅니다. 방법으로 회신 [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)합니다.  
  
 EVENT_STOPPING  
 Stopping 이벤트 임을 나타냅니다. 사용 하 여 결합 해야 `EVENT_ASYNCHRONOUS` 또는 `EVENT_SYNCHRONOUS`합니다.  
  
 EVENT_ASYNC_STOP  
 비동기 중지 이벤트를 나타냅니다. 이런 이벤트가 현재입니다. 이 플래그는 유일한 기능입니다.  
  
 EVENT_SYNC_STOP  
 동기 stopping 이벤트를 나타냅니다 (의 조합을 `EVENT_SYNCHRONOUS` 및 `EVENT_STOPPING`). 중지 이벤트를 보낼 때이 값은 디버그 엔진 (DE)에 의해 사용 됩니다. 회신을 호출 하 여 이루어집니다 [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md), [단계](../../../extensibility/debugger/reference/idebugprogram2-step.md), 또는 [계속](../../../extensibility/debugger/reference/idebugprogram2-continue.md)합니다.  
  
 EVENT_IMMEDIATE  
 IDE에 즉시, 동기적으로 전송 되는 이벤트를 나타냅니다. 이 플래그와 같은 다른 플래그와 함께 결합 `EVENT_ASYNCHRONOUS`, `EVENT_SYNCHRONOUS`, 또는 `EVENT_SYNC_STOP` 이벤트 (있는 경우)는 회신 메커니즘 알려져 팩트의 유형을 나타내는입니다.  
  
 EVENT_EXPRESSION_EVALUATION  
 이벤트 식 평가의 결과입니다.  
  
## <a name="remarks"></a>설명  
 이러한 값이 전달 되는 `dwAttrib` 의 매개 변수는 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 메서드.  
  
 이러한 값에 비트와 함께 사용할 수 있습니다 `OR`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)