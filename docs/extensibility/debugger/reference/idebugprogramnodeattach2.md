---
title: IDebugProgramNodeAttach2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramNodeAttach2
helpviewer_keywords:
- IDebugProgramNodeAttach2 interface
ms.assetid: 46b37ac9-a026-4ad3-997b-f19e2f8deb73
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a83f5635dfacb638a2e76054dc5ed4e887e2a3cb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogramnodeattach2"></a>IDebugProgramNodeAttach2
프로그램 노드를를 연결 된 프로그램에 연결 하지 못했습니다. 알림을 받을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProgramNodeAttach2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 인터페이스를 구현 하는 동일한 클래스에서 구현 됩니다는 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스 연결 작업에 대 한 알림을 수신 하려면 및 연결 작업을 취소할 수 있도록 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 가져올는 `QueryInterface` 에서 메서드는 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 개체입니다. [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드를 호출 하기 전에 해야는 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드 연결 프로세스를 중지 하려면 프로그램 노드에 제공할 수 있도록 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 이 인터페이스는 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)|연결 된 프로그램에 연결 하거나 연결 프로세스를 지연 된 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 사용 되지 않는를 기본 설정된 대체 [Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md) 메서드. 모든 디버그 엔진은 항상와 로드는 `CoCreateInstance` 함수, 즉, 디버깅 중인 프로그램의 주소 공간 외부 인스턴스화됩니다.  
  
 이전 구현 하는 경우는 `IDebugProgramNode2::Attach_V7` 메서드를 설정 하면는 `GUID` 디버깅 중인 프로그램을 다음만의 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드를 구현 해야 합니다.  
  
 이전 구현 하는 경우는 `IDebugProgramNode2::Attach_V7` 기능을 하는의 구현으로 이동 해야 합니다. 그런 다음 제공 된 콜백 인터페이스를 사용 하는 메서드는 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드 및 `IDebugProgramNodeAttach2` 인터페이스에는 없음 구현 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)