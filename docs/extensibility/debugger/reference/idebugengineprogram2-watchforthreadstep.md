---
title: IDebugEngineProgram2::WatchForThreadStep | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineProgram2::WatchForThreadStep
helpviewer_keywords:
- IDebugEngineProgram2::WatchForThreadStep
ms.assetid: b70922a3-1313-409a-b3b7-50c7cd13e394
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3f7c897c4c5b8488766f72723f3e85909281abbf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugengineprogram2watchforthreadstep"></a>IDebugEngineProgram2::WatchForThreadStep
실행에 대 한 감시 (또는 실행에 대 한 감시 중지) 지정한 스레드에서 발생 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT WatchForThreadStep(   
   IDebugProgram2* pOriginatingProgram,  
   DWORD           dwTid,  
   BOOL            fWatch,  
   DWORD           dwFrame  
);  
```  
  
```csharp  
int WatchForThreadStep(   
   IDebugProgram2 pOriginatingProgram,  
   uint           dwTid,  
   int            fWatch,  
   uint           dwFrame  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pOriginatingProgram`  
 [in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 도 실행 되 고 프로그램을 나타내는 개체입니다.  
  
 `dwTid`  
 [in] 조사할 스레드의 식별자를 지정 합니다.  
  
 `fWatch`  
 [in] 0이 아닌 (`TRUE`) 수단으로 식별 하는 스레드에서 실행에 대 한 감시 시작 `dwTid`, 그렇지 않으면 0 (`FALSE`)에서 실행을 위해 시청 의미 중지 `dwTid`합니다.  
  
 `dwFrame`  
 [in] 단계 유형을 제어 하는 프레임 인덱스를 지정 합니다. 이 값은 영 (0), 단계 형식이 "한 단계씩 코드 실행" 하 고 스레드가로 식별 될 때마다 프로그램이 중지 해야 `dwTid` 실행 합니다. 때 `dwFrame` 0이 아닌, 단계 형식이 "프로시저 단위로 실행" 하 고 스레드가으로 식별 하는 경우에 프로그램이 중지 해야 `dwTid` 인덱스는 8, 보다는 스택의 상위 프레임에서 실행 되 고 `dwFrame`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 세션 디버그 관리자 (SDM)로 식별 되는 프로그램을 설명 하는 경우는 `pOriginatingProgram` 매개 변수를 알립니다 다른 모든 연결 된 프로그램은이 메서드를 호출 하 여 합니다.  
  
 이 방법은 동일한 스레드에서 단계별 실행에 적용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)