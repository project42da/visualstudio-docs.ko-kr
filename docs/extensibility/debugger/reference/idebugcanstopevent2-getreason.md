---
title: IDebugCanStopEvent2::GetReason | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCanStopEvent2::GetReason
helpviewer_keywords: IDebugCanStopEvent2::GetReason
ms.assetid: f5de31ca-7b8d-4029-9cf9-ba860ac66af6
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 785fed3d89ab6a351a82a61acbd3f58978a690e5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugcanstopevent2getreason"></a>IDebugCanStopEvent2::GetReason
디버그 엔진 (DE)를 중지 하려고 하는 이유는 이유를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetReason(   
   CANSTOP_REASON* pcr  
);  
```  
  
```csharp  
int GetReason(   
   out enum_CANSTOP_REASON pcr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcr`  
 [out] 값을 반환 된 [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md) 이 이벤트에 대 한 이유를 설명 하는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 일반적으로 하기 전에 호출 됩니다는 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md) 메서드 호출자에 게는 0이 아닌를 전달할지 여부를 결정할 수 있도록 (`TRUE`)에 `IDebugCanStopEvent2::CanStop` 메서드.  
  
 이유로 중지 될 수 있습니다 `CANSTOP_ENTRYPOINT`, 즉는 DE는 진입점에 도달 했습니다 또는 `CANSTOP_STEPIN`, 함수 한 단계씩에 DE 의미입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)   
 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)