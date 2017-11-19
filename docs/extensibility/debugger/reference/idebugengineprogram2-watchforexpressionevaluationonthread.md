---
title: IDebugEngineProgram2::WatchForExpressionEvaluationOnThread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
helpviewer_keywords: IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
ms.assetid: 01d05e77-8cac-4d1b-b19f-25756767ed27
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dbb3437edc8d357e6a4e96eed9bf9881970a01c9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugengineprogram2watchforexpressionevaluationonthread"></a>IDebugEngineProgram2::WatchForExpressionEvaluationOnThread
허용 (하거나 허용 하지 않는) 프로그램이 중지 된 경우에 해당 스레드에서 발생 되는 식 계산 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT WatchForExpressionEvaluationOnThread(   
   IDebugProgram2*       pOriginatingProgram,  
   DWORD                 dwTid,  
   DWORD                 dwEvalFlags,  
   IDebugEventCallback2* pExprCallback,  
   BOOL                  fWatch  
);  
```  
  
```csharp  
int WatchForExpressionEvaluationOnThread(   
   IDebugProgram2       pOriginatingProgram,  
   uint                  dwTid,  
   uint                  dwEvalFlags,  
   IDebugEventCallback2 pExprCallback,  
   int                   fWatch  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pOriginatingProgram`  
 [in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 은 식을 평가 하 여 프로그램을 나타내는 개체입니다.  
  
 `dwTid`  
 [in] 스레드 식별자를 지정합니다.  
  
 `dwEvalFlags`  
 [in] 플래그의 조합 된 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 계산을 수행할 수는 하는 방법을 지정 하는 열거형입니다.  
  
 `pExprCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 식 평가 중에 발생 하는 디버그 이벤트를 보내는 데 사용할 개체입니다.  
  
 `fWatch`  
 [in] 0이 아닌 경우 (`TRUE`)로 식별 되는 스레드에서 식 평가 사용 하면 `dwTid`, 그렇지 않으면 0 (`FALSE`) 해당 스레드에서 식 평가 허용 하지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 세션 디버그 관리자 (SDM)로 식별 되는 프로그램을 요청 하는 경우는 `pOriginatingProgram` 매개 변수는 식을 계산 하기 위해이 메서드를 호출 하 여 연결 된 다른 모든 프로그램에 게 알려 줍니다.  
  
 한 프로그램에서 식 계산에서 코드를 실행, 함수 평가 또는 모든 평가 인해 발생할 수 있습니다 `IDispatch` 속성입니다. 이 인해이 메서드를 실행 하 고이 프로그램에서 스레드가 중지 될 수 있습니다 하는 경우에 완료 식 평가 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)