---
title: IDebugPortEvents2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortEvents2
helpviewer_keywords: IDebugPortEvents2 interface
ms.assetid: 2c017094-3ba2-4067-83f9-147df1d96bce
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0a5782f0a50ac37b45c4b7e3402bcdded96b4683
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportevents2"></a>IDebugPortEvents2
이 인터페이스는 프로세스 및 프로그램 만들기 및 소멸 특정 포트에서의 수신기를 (일반적으로 세션 디버그 관리자 [SDM] 또는 디버그 엔진)에 게 알립니다. 프로세스 및 포트에서 실행 중인 프로그램의 실시간 보기를 표시 하이 정보를 사용할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPortEvents2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 Visual Studio에는 일반적으로 프로그램 생성 및 소멸에 대 한 알림을 수신 하려면이 인터페이스를 구현 합니다. 디버그 엔진 이러한 포트 이벤트를 수신 하도록이 인터페이스를 구현할 수도 있습니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 모든 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 한 인터페이스를 쿼리할 수는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> 인터페이스입니다. 그런 다음 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.FindConnectionPoint%2A> 방법을 `IDebugPortEvents2` 에서 호출 되는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> 가져올 인터페이스는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> 인터페이스입니다. 마지막으로 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> 에서 메서드는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> 인터페이스를 통해 이벤트를 전송 하기 위해 호출 됩니다는 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md) 메서드.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugPortEvents2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[Event](../../../extensibility/debugger/reference/idebugportevents2-event.md)|생성 및 소멸 프로세스 및 포트에서 프로그램을 설명 하는 이벤트를 보냅니다.|  
  
## <a name="remarks"></a>설명  
 `IDebugPortEvents2`또한은 SDM에서 이미 디버깅 중인 프로세스에서 실행 되는 프로그램을 디버깅할 합니다.  
  
 포트 이벤트는이 인터페이스는 SDM에 전달 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)