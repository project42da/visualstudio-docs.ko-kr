---
title: "IDebugEngine2::CreatePendingBreakpoint | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngine2::CreatePendingBreakpoint"
helpviewer_keywords: 
  - "IDebugEngine2::CreatePendingBreakpoint"
ms.assetid: 92e85b90-a931-48d9-89a7-a6edcb83ae5a
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugEngine2::CreatePendingBreakpoint
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

보류 중단점의 디버그 엔진 \(DE\)를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT CreatePendingBreakpoint(   
   IDebugBreakpointRequest2*  pBPRequest,  
   IDebugPendingBreakpoint2** ppPendingBP  
);  
```  
  
```c#  
int CreatePendingBreakpoint(   
   IDebugBreakpointRequest2     pBPRequest,  
   out IDebugPendingBreakpoint2 ppPendingBP  
);  
```  
  
#### 매개 변수  
 `pBPRequest`  
 \[in\] [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) 개체를 만들려면 보류 중단점에 설명 합니다.  
  
 `ppPendingBP`  
 \[out\] 반환 된 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) 보류 중단점을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  일반적으로 반환 `E_FAIL` 경우는 `pBPRequest` 매개 변수의 경우 DE에서 지 원하는 모든 언어와 일치 하지 않습니다을 `pBPRequest` 잘못 되었거나 완전 하지 않은 매개 변수입니다.  
  
## 설명  
 보류 중단점은 코드에 중단점을 바인딩하는 데 필요한 모든 정보를 기본적으로입니다.  이 메서드에서 반환 된 보류 중단점이 코드까지 바인딩되어 있지 않습니다는 [바인딩](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) 메서드가 호출 됩니다.  
  
 각 보류 중단점에 대해 사용자 설정 세션 디버그 매니저 \(SDM\)이이 메서드를 각 연결 된 DE에서 호출 합니다.  DE 중단점이 해당 DE에서 실행 되는 프로그램에 대 한 유효성을 검사 하는 것입니다.  
  
 사용자 코드 줄에 중단점을 설정 하는 경우는 DE의 가장 가까운 줄로이 코드에 해당 하는 문서 중단점을 바인딩할 수 있습니다.  이렇게 하면 사용자가 문 여러 줄의 첫 번째 줄에 중단점을 설정 하 여 \(특성을 여기서 모든 코드에 디버그 정보가 사용\) 마지막 줄에 바인딩할 수 있습니다.  
  
## 예제  
 다음 예제에서는 단순에이 메서드를 구현 하는 방법을 보여 줍니다. `CProgram` 개체입니다.  DE의 구현에 `IDebugEngine2::CreatePendingBreakpoint` 다음이 각 프로그램에서 메서드이 구현에 대 한 모든 호출을 전달할 수 있습니다.  
  
```  
HRESULT CProgram::CreatePendingBreakpoint(IDebugBreakpointRequest2* pBPRequest, IDebugPendingBreakpoint2** ppPendingBP)     
{    
  
   // Create and initialize the CPendingBreakpoint object.  
   CComObject<CPendingBreakpoint> *pPending;    
   CComObject<CPendingBreakpoint>::CreateInstance(&pPending);    
   pPending->Initialize(pBPRequest, m_pInterp, m_pCallback, m_pEngine);    
   return pPending->QueryInterface(ppPendingBP);    
}    
```  
  
## 참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [바인딩](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)   
 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)