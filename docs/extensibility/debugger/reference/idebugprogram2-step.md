---
title: IDebugProgram2::Step | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgram2::Step
helpviewer_keywords:
- IDebugProgram2::Step
ms.assetid: e4c2ffce-9810-4088-8162-eac9ef04f2a9
caps.latest.revision: 16
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a7142f79f4406611eb4ab3cbb6695cb2d0305bed
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram2step"></a>IDebugProgram2::Step
단계를 수행합니다.  
  
> [!NOTE]
>  이 메서드는 사용 되지 않습니다. 사용 하 여 [단계](../../../extensibility/debugger/reference/idebugprocess3-step.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Step(   
   IDebugThread2*  pThread,  
   STEPKIND        sk,  
   STEPUNIT        step  
);  
```  
  
```csharp  
int Step(   
   IDebugThread2  pThread,  
   enum_STEPKIND  sk,  
   enum_STEPUNIT  step  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pThread`  
 [in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 도 실행 중인 스레드를 나타내는 개체입니다.  
  
 `sk`  
 [in] 값은 [STEPKIND](../../../extensibility/debugger/reference/stepkind.md) 단계의 종류를 지정 하는 열거형입니다.  
  
 `step`  
 [in] 값은 [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md) (예를 들어 하 여 문 또는 명령)의 단계 단위를 지정 하는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 모든 스레드 동기화 또는 스레드 간의 통신 된 경우에 특정 스레드를 진행 하는 프로그램의 다른 스레드를 실행 해야 합니다.  
  
> [!WARNING]
>  Stopping 이벤트 또는 즉시 (동기) 이벤트를 보내지 않음 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 이 호출을 처리 하는 동안 그렇지 않은 경우 디버거가 중단 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)