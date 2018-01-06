---
title: IDebugMessageEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMessageEvent2
helpviewer_keywords: IDebugMessageEvent2 interface
ms.assetid: a9ff3d00-e9ac-4cd6-bda9-584a4815aff8
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5e14e8ea2df83520724b9f6663c9624d54cf772c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmessageevent2"></a>IDebugMessageEvent2
이 인터페이스는 메시지를 보내는 사용자의 응답을 필요로 하는 Visual studio 디버그 엔진 (DE)에 의해 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugMessageEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 사용자 응답을 필요로 하는 Visual Studio로 메시지를 보내려고이 인터페이스를 구현 합니다. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 해당이 인터페이스와 같은 개체에 대해 인터페이스를 구현 해야 합니다. SDM 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 액세스로는 `IDebugEvent2` 인터페이스입니다.  
  
 이 인터페이스의 구현을의 Visual Studio의 전화 통신 해야 [SetResponse](../../../extensibility/debugger/reference/idebugmessageevent2-setresponse.md) 는 DE에 있습니다. 예를 들어 스레드를 처리 하는 DE의 메시지에 게시 된 메시지와 함께이 작업을 수행할 수 있습니다 또는이 인터페이스를 구현 하는 개체는 DE에 대 한 참조을로 전달 된 응답으로는 DE 다시 호출할 수 `IDebugMessageEvent2::SetResponse`합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 DE을 만들어 응답이 필요한 사용자에 게 메시지를 표시 하려면이 이벤트 개체를 보냅니다. 이벤트를 사용 하 여 보내집니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 될 때은 SDM에서 제공 되는 콜백 함수입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugMessageEvent2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)|표시할 메시지를 가져옵니다.|  
|[SetResponse](../../../extensibility/debugger/reference/idebugmessageevent2-setresponse.md)|있는 경우 messagebox에서 응답을 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 DE 특정 메시지에 대 한 사용자에 게 서 특정 응답 해야 하는 경우이 인터페이스를 사용 합니다. 예를 들어는 DE 프로그램에 원격으로 연결 하려고 시도한 후 "액세스 거부" 메시지를 가져오는 경우는 DE이 특정 메시지를 보냅니다에서 Visual Studio는 `IDebugMessageEvent2` 메시지 상자 스타일을 사용 하 여 이벤트 `MB_RETRYCANCEL`합니다. 이렇게 하면 사용자를 다시 시도 하거나 연결 작업을 취소 합니다.  
  
 DE이이 메시지의 Win32 함수 규칙에 따라 처리 되는 방법을 지정 `MessageBox` (참조 [AfxMessageBox](http://msdn.microsoft.com/Library/d66d0328-cdcc-48f6-96a4-badf089099c8) 세부 정보에 대 한).  
  
 사용 하 여는 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md) 사용자 로부터 응답을 필요로 하지 않는 Visual Studio에 메시지를 보낼 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)