---
title: IDebugEngine2::CreatePendingBreakpoint | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::CreatePendingBreakpoint
helpviewer_keywords:
- IDebugEngine2::CreatePendingBreakpoint
ms.assetid: 92e85b90-a931-48d9-89a7-a6edcb83ae5a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a0813e077d8bdc2ba024dc932a6cb571b1b2fed
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugengine2creatependingbreakpoint"></a>IDebugEngine2::CreatePendingBreakpoint
디버그 엔진 (DE)에 보류 중인 중단점을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreatePendingBreakpoint(   
   IDebugBreakpointRequest2*  pBPRequest,  
   IDebugPendingBreakpoint2** ppPendingBP  
);  
```  
  
```csharp  
int CreatePendingBreakpoint(   
   IDebugBreakpointRequest2     pBPRequest,  
   out IDebugPendingBreakpoint2 ppPendingBP  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pBPRequest`  
 [in] [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) 만들려는 보류 중인 중단점에 설명 하는 개체입니다.  
  
 `ppPendingBP`  
 [out] 반환 된 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) 보류 중단점을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 일반적으로 반환 `E_FAIL` 경우는 `pBPRequest` 매개 변수의 경우 DE에서 지 원하는 모든 언어에 맞지 않습니다는 `pBPRequest` 매개 변수가 잘못 되었거나 불완전 합니다.  
  
## <a name="remarks"></a>설명  
 보류 중인 중단점은 기본적으로 코드에 중단점을 바인딩할 때 필요한 모든 정보의 컬렉션입니다. 보류 중인 중단점이 메서드에서 반환 될 때까지 코드에 바인딩되지 않은 [바인딩할](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) 메서드를 호출 합니다.  
  
 중단점 보류 중인 각 사용자 집합 세션 디버그 관리자 (SDM)이이 메서드를 호출에 연결 된 각 DE 합니다. DE 중단점이 해당 DE에서 실행 중인 프로그램에 대해 올바른지 확인 하는 합니다.  
  
 사용자 코드의 줄에 중단점을 설정한 경우 때는 DE는이 코드에 해당 하는 문서에는 가장 가까운 줄에 중단점을 바인딩할 수 있습니다. 따라서 사용자는 여러 줄 문의 첫 번째 줄에 중단점을 설정 하지만 마지막 줄 (여기서 모든 코드 특성 사용에 디버그 정보)에 바인딩할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 간단한에이 메서드를 구현 하는 방법을 보여 줍니다 `CProgram` 개체입니다. DE 구현의 `IDebugEngine2::CreatePendingBreakpoint` 다음 각 프로그램의 메서드의이 구현에 대 한 모든 호출을 전달할 수 없습니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [바인딩](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)   
 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)