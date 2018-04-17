---
title: IDebugProcess3::Continue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcess3::Continue
helpviewer_keywords:
- IDebugProcess3::Continue
ms.assetid: 57506242-5763-4c08-adb9-8a78ce02cebb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 38bb11237d5016e3747c5a615e61144511c17fad
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprocess3continue"></a>IDebugProcess3::Continue
계속 중지 된 상태에서이 프로세스를 실행 합니다. 이전 실행 상태 (예: 단계)는 유지, 프로세스를 다시 실행을 시작 합니다.  
  
> [!NOTE]
>  이 메서드를 대신 사용 해야 [계속](../../../extensibility/debugger/reference/idebugprogram2-continue.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Continue(  
   IDebugThread2* pThread  
);  
```  
  
```csharp  
int Continue(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pThread`  
 [in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 계속 실행 되어야 하는 스레드를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버깅 중인 프로세스가 개수, 또는 중지 이벤트를 생성 하는 프로세스에 관계 없이이 프로세스에서 호출 됩니다. 구현 (예: 단계) 이전 실행 상태를 유지 하 고의 이전 실행을 완료 하기 전에 중지 되지 것 처럼 계속 실행 해야 합니다. 즉, 경우에 스레드가이 프로세스 단계 조치 작업을 수행 중 이었던 작업 및 중지 하 여 일부 다른 프로세스를 중지 했습니다 차례로 `Continue` 를 호출 했지만 지정 된 스레드가 원래 단계씩 작업을 완료 해야 합니다.  
  
 **경고** stopping 이벤트 또는 즉시 (동기) 이벤트를 보내지 않습니다 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 이 호출을 처리 하는 동안 그렇지 않은 경우 디버거가 중단 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)