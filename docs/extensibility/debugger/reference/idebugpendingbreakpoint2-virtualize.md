---
title: IDebugPendingBreakpoint2::Virtualize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPendingBreakpoint2::Virtualize
helpviewer_keywords:
- Virtualize method
- IDebugPendingBreakpoint2::Virtualize method
ms.assetid: 58c8e9a5-4494-47c2-bddb-56f628da6a2d
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 98a4184813f424357dcc6fdecf87289351022dc0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpendingbreakpoint2virtualize"></a>IDebugPendingBreakpoint2::Virtualize
이 중단점이 보류 중인 가상화 된 상태를 토글합니다. 보류 중인 중단점 가상화 되는 새 코드를 프로그램에 로드 될 때마다 바인딩할 디버그 엔진 시도 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Virtualize(   
   BOOL fVirtualize  
);  
```  
  
```cpp  
int Virtualize(   
   int fVirtualize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fVirtualize`  
 [in] 에 0이 아닌 설정 (`TRUE`) 보류 중인 중단점을 가상화 할 또는 0 (`FALSE`) 가상화 사용 하지 않으려면입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 반환 `E_BP_DELETED` 중단점 삭제 된 경우.  
  
## <a name="remarks"></a>설명  
 가상화 된 중단점은 코드가 로드 될 때마다 바인딩되어 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 간단한에이 메서드를 구현 하는 방법을 보여 줍니다 `CPendingBreakpoint` 공개 하는 개체는 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) 인터페이스입니다.  
  
```cpp  
HRESULT CPendingBreakpoint::Virtualize(BOOL fVirtualize)    
{    
   HRESULT hr;    
  
   // Verify that the pending breakpoint has not been deleted. If deleted,   
   // then return hr = E_BP_DELETED.    
   if (m_state.state != PBPS_DELETED)    
   {    
      if (fVirtualize)    
      {    
         // Set the PBPSF_VIRTUALIZED flag in the PENDING_BP_STATE_FLAGS   
         // structure.    
         SetFlag(m_state.flags, PBPSF_VIRTUALIZED);    
      }    
      else    
      {    
         // Clear the PBPSF_VIRTUALIZED flag in the PENDING_BP_STATE_FLAGS   
         // structure.    
         ClearFlag(m_state.flags, PBPSF_VIRTUALIZED);    
      }    
      hr = S_OK;    
   }    
   else    
   {    
      hr = E_BP_DELETED;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)