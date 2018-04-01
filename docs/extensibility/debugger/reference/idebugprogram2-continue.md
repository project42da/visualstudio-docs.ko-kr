---
title: IDebugProgram2::Continue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgram2::Continue
helpviewer_keywords:
- IDebugProgram2::Continue
ms.assetid: e5a6e02a-d21b-4a03-a034-e8de1f71ce2e
caps.latest.revision: 12
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5c90c456c4825ea9da054f7e78621493cc90a648
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram2continue"></a>IDebugProgram2::Continue
중지 된 상태에서이 프로그램을 실행을 계속 합니다. 이전 실행 상태 (예: 단계)는 유지, 프로그램 실행을 다시 시작 합니다.  
  
> [!NOTE]
>  이 메서드는 사용 되지 않습니다. 사용 하 여 [계속](../../../extensibility/debugger/reference/idebugprocess3-continue.md) 메서드 대신 합니다.  
  
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
 [in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 스레드를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버깅 중인 프로그램 수, 또는 중지 이벤트를 생성 하는 응용 프로그램에 관계 없이이 프로그램에 호출 됩니다. 구현 (예: 단계) 이전 실행 상태를 유지 하 고의 이전 실행을 완료 하기 전에 중지 되지 것 처럼 계속 실행 해야 합니다. 즉,이 프로그램에 한 단계씩 작업 수행 되 던 스레드와 다른 프로그램이 중지 하 고이 메서드가 호출 된 후 중지 되었습니다, 프로그램 원래의 단계씩 작업을 완료 해야 합니다.  
  
> [!WARNING]
>  Stopping 이벤트 또는 즉시 (동기) 이벤트를 보내지 않음 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 이 호출을 처리 하는 동안 그렇지 않은 경우 디버거가 중단 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)