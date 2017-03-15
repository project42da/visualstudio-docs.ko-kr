---
title: "IDebugPendingBreakpoint2::Delete | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPendingBreakpoint2::Delete"
helpviewer_keywords: 
  - "IDebugPendingBreakpoint2::Delete 메서드"
  - "Delete 메서드"
ms.assetid: 4cb5ed81-6f0c-41ce-a770-5adb6b4bf5d9
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugPendingBreakpoint2::Delete
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 보류 중단점 및 바인딩된에서 모든 중단점을 삭제 합니다.  
  
## 구문  
  
```cpp#  
HRESULT Delete(   
   void   
);  
```  
  
```c#  
int Delete();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_BP_DELETED` 중단점 삭제 된 경우입니다.  
  
## 예제  
 다음 예제에서는 단순에이 메서드를 구현 하는 방법을 보여 줍니다. `CPendingBreakpoint` 를 구현 하는 개체는 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) 인터페이스입니다.  
  
```cpp#  
HRESULT CPendingBreakpoint::Delete(void)    
{    
   HRESULT hr;    
  
   // Verify that the pending breakpoint has not been deleted. If deleted,    
   // then return hr = E_BP_DELETED.    
   if (m_state.state != PBPS_DELETED)    
   {    
      // If the pending breakpoint has bound and has an associated bound   
      // breakpoint, delete and release the bound breakpoint and set the   
      // pointer to NULL.    
      if (m_pBoundBP)    
      {    
         m_pBoundBP->Delete();    
         m_pBoundBP->Release();    
         m_pBoundBP = NULL;    
      }    
      // If the pending breakpoint did not bind and has an associated   
      // error breakpoint, release the error breakpoint and set the   
      // pointer to NULL.   
      if (m_pErrorBP)    
      {    
         m_pErrorBP->Release();    
         m_pErrorBP = NULL;    
      }    
  
      // Set the PENDING_BP_STATE in the PENDING_BP_STATE_INFO structure   
      // to deleted.     
      m_state.state = PBPS_DELETED;    
   }    
   else    
   {    
      hr = E_BP_DELETED;    
   }    
  
   return hr;    
}    
```  
  
## 참고 항목  
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)