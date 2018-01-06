---
title: IDebugBoundBreakpoint2::Enable | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBoundBreakpoint2::Enable
helpviewer_keywords:
- Enable method
- IDebugBoundBreakpoint2::Enable method
ms.assetid: 1b4e3f73-c94d-4aa3-9aa8-0d8cb8a6c5ca
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0372595eb0848167bcc8baac307cd6d4bd5fc01f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugboundbreakpoint2enable"></a>IDebugBoundBreakpoint2::Enable
중단점을 해제 하거나 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Enable(   
   BOOL fEnable  
);  
```  
  
```csharp  
int Enable(   
   int fEnable  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fEnable`  
 [in] 0이 아닌 설정 (`TRUE`) 사용 하도록 설정 하려면 또는 0 (`FALSE`)에 중단점을 해제 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 반환 `E_BP_DELETED` 바인딩된 중단점 개체의 상태로 설정 됩니다 `BPS_DELETED` (의 일부는 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md) 열거형)입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 간단한에이 메서드를 구현 하는 방법을 보여 줍니다 `CBoundBreakpoint` 공개 하는 개체는 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md) 인터페이스입니다.  
  
```  
HRESULT CBoundBreakpoint::Enable(BOOL fEnable)    
{    
   HRESULT hr;    
  
   // Verify that the bound breakpoint has not been deleted. If deleted,   
   // then return hr = E_BP_DELETED.    
   if (m_state != BPS_DELETED)    
   {    
      // Check the state of the bound breakpoint. If the breakpoint is  
      // supposed to be, but has not already been, enabled, then have the  
      // interpreter set the breakpoint.    
      if (fEnable && m_state != BPS_ENABLED)    
      {    
         hr = m_pInterp->SetBreakpoint(m_sbstrDoc, this);    
         if (hr == S_OK)    
         {    
            // Change the state of the breakpoint to BPS_ENABLED.    
            m_state = BPS_ENABLED;    
         }    
      }    
      // Check the state of the bound breakpoint. If the breakpoint is   
      // supposed to be, but has not already been, disabled, then have the   
      // interpreter remove the breakpoint.    
      else if (!fEnable && m_state != BPS_DISABLED)    
      {    
         hr = m_pInterp->RemoveBreakpoint(m_sbstrDoc, this);    
         if (hr == S_OK)    
         {    
            // Change the state of the breakpoint to BPS_DISABLED.    
            m_state = BPS_DISABLED;    
         }    
      }    
      else    
      {    
         hr = S_FALSE;    
      }    
   }    
   else    
   {    
      hr = E_BP_DELETED;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)