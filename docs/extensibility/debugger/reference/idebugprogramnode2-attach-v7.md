---
title: IDebugProgramNode2::Attach_V7 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramNode2::Attach
helpviewer_keywords:
- IDebugProgramNode2::Attach_V7
- IDebugProgramNode2::Attach
ms.assetid: b5ffc736-efc7-4ca8-964d-5536ff891b0e
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9ba26d779d89944cb4f8852cbb7354f31c54cd8e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogramnode2attachv7"></a>IDebugProgramNode2::Attach_V7
사용 되지 않습니다. 사용 하지 마십시오.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Attach_V7 (   
   IDebugProgram2*       pMDMProgram,  
   IDebugEventCallback2* pCallback,  
   DWORD                 dwReason  
);  
```  
  
```csharp  
int Attach_V7 (   
   IDebugProgram2       pMDMProgram,  
   IDebugEventCallback2 pCallback,  
   uint                 dwReason  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pMDMProgram`  
 [in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 연결할 프로그램을 나타내는 인터페이스입니다.  
  
 `pCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 은 SDM에 디버그 이벤트를 보내는 데 사용할 인터페이스입니다.  
  
 `dwReason`  
 [in] 값은 [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) 연결에 대 한 이유를 지정 하는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 구현을 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="remarks"></a>설명  
  
> [!WARNING]
>  일부로 [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)],이 메서드는 더 이상 사용 하며 항상 반환 `E_NOTIMPL`합니다. 참조는 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md) 프로그램 노드를 연결할 수 없습니다 나타내는 경우 또는 프로그램 노드 프로그램을 설정 하 고 간단히 경우 다른 방법에 대 한 인터페이스 `GUID`합니다. 그렇지 않은 경우 구현에서 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드.  
  
## <a name="prior-to-visual-studio-2005"></a>Visual Studio 2005 이전  
 이 메서드는 DE 디버깅 중인 프로그램의 주소 공간에서 실행 하는 경우에 구현 해야 합니다. 그렇지 않으면이 메서드에서 반환 해야 `S_FALSE`합니다.  
  
 이 메서드를 호출할 때는 DE 보내야는 [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md) 이미이 인스턴스에 대 한 전송 되지 않은 경우 이벤트 개체는 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 인터페이스를으로 [ IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 및 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 이벤트 개체입니다. [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md) 이벤트 개체는 다음 경우는 `dwReason` 매개 변수는 `ATTACH_REASON_LAUNCH`합니다.  
  
 DE 호출 해야 합니다는 [GetProgramId](../../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) 에서 메서드는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 에서 제공 된 개체는 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) 이벤트 개체를 해당 프로그램의 GUID를 저장 해야 합니다 에 대 한 인스턴스 데이터에는 `IDebugProgram2` 는 DE에 의해 구현 되는 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)   
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)   
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)   
 [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)   
 [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md)