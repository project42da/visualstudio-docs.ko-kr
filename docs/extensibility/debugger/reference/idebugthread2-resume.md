---
title: IDebugThread2::Resume | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugThread2::Resume
helpviewer_keywords: IDebugThread2::Resume
ms.assetid: 36aad682-b0b9-40a2-b3fc-f0e61d41cdbc
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5de844c3b07a509f266e2f9d278d1f78bea2b089
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugthread2resume"></a>IDebugThread2::Resume
스레드의 실행을 다시 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Resume (   
   DWORD *pdwSuspendCount  
);  
```  
  
```csharp  
int Resume (   
   out uint pdwSuspendCount  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwSuspendCount`  
 [out] 다시 시작 작업 후 일시 중단 횟수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드 감소를 호출할 때마다 일시 중단 횟수가 실행이 실제로 다시 시작 될 때 0, 도달할 때까지 합니다. 이 일시 중단 횟수가에 표시 되는 **스레드** 디버그 창.  
  
 이 메서드를 호출할 때마다, 이전에 호출 되어야는 [Suspend](../../../extensibility/debugger/reference/idebugthread2-suspend.md) 메서드. 일시 중단 횟수가 결정 횟수는 `IDebugThread2::Suspend` 지금까지 메서드가 호출 되었습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Suspend](../../../extensibility/debugger/reference/idebugthread2-suspend.md)