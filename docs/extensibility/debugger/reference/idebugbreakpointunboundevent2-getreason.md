---
title: IDebugBreakpointUnboundEvent2::GetReason | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBreakpointUnboundEvent2::GetReason
helpviewer_keywords: IDebugBreakpointUnboundEvent2::GetReason
ms.assetid: 0f8a4fec-d3eb-417d-8516-4f7b51904033
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3f11678db25c15e8c17a3f28214a146a90abbba7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugbreakpointunboundevent2getreason"></a>IDebugBreakpointUnboundEvent2::GetReason
중단점이 바인딩된 없습니다. 이유를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetReason(   
   BP_UNBOUND_REASON* pdwUnboundReason  
);  
```  
  
```csharp  
int GetReason(   
   out enum_ BP_UNBOUND_REASON pdwUnboundReason  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwUnboundReason`  
 [out] 값을 반환 된 [BP_UNBOUND_REASON](../../../extensibility/debugger/reference/bp-unbound-reason.md) 중단점이 바인딩된 없습니다. 이유를 지정 하는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이유는 편집 하며 계속 하기 작업 또는 중단점 오류에 바인딩 되었습니다 결정 한 후 다른 위치로 다시 바인딩할 되 고 중단점을 포함 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에 대 한이 메서드를 구현 하는 방법을 보여 줍니다는 **CBreakpointUnboundDebugEventBase** 공개 하는 개체는 [IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md) 인터페이스입니다.  
  
```cpp  
STDMETHODIMP CBreakpointUnboundDebugEventBase::GetReason(  
    BP_UNBOUND_REASON* pdwUnboundReason)  
{  
    HRESULT hRes = E_FAIL;  
  
    if ( EVAL(pdwUnboundReason) )  
    {  
        *pdwUnboundReason = m_dwReason;  
  
        hRes = S_OK;  
    }  
    else  
        hRes = E_INVALIDARG;  
  
    return ( hRes );  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)