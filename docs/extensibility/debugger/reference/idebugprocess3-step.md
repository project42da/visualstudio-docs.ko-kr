---
title: IDebugProcess3::Step | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess3::Step
helpviewer_keywords: IDebugProcess3::Step
ms.assetid: 6ad9094c-27cc-4927-8a7c-1b4d97b2e436
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d7bd62bc141e3c5c63a887f683b7e252d466ea83
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprocess3step"></a>IDebugProcess3::Step
하나의 명령 또는 문을 한 단계씩 실행을 처리를 수행 합니다.  
  
> [!NOTE]
>  이 메서드를 대신 사용 해야 [단계](../../../extensibility/debugger/reference/idebugprogram2-step.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Step(  
   IDebugThread2* pThread,  
   STEPKIND       sk,  
   STEPUNIT       step,  
);  
```  
  
```csharp  
int Step(  
   IDebugThread2 pThread,   
   enum_STEPKIND sk,   
   enum_STEPUNIT step  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pThread`  
 [in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 도 실행 중인 스레드를 나타내는 개체입니다.  
  
 `sk`  
 [in] 중 하나는 [STEPKIND](../../../extensibility/debugger/reference/stepkind.md) 값입니다.  
  
 `step`  
 [in] 중 하나는 [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md) 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 모든 스레드 동기화 또는 스레드 간의 통신 된 경우에 특정 스레드를 진행 하는 프로세스의 다른 스레드를 실행 해야 합니다.  
  
 **경고** stopping 이벤트 또는 즉시 (동기) 이벤트를 보내지 않습니다 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 이 호출을 처리 하는 동안 그렇지 않은 경우 디버거가 중단 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [STEPKIND](../../../extensibility/debugger/reference/stepkind.md)   
 [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)