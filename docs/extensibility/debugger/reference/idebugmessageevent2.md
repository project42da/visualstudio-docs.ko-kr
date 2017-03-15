---
title: "IDebugMessageEvent2 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugMessageEvent2
helpviewer_keywords:
- IDebugMessageEvent2 interface
ms.assetid: a9ff3d00-e9ac-4cd6-bda9-584a4815aff8
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 0f033c5793dc3b89a1f2bd74a2bc4857730fb746
ms.lasthandoff: 02/22/2017

---
# <a name="idebugmessageevent2"></a>IDebugMessageEvent2
이 인터페이스는 메시지를 보내는 사용자의 응답을 필요로 하는 Visual studio 디버그 엔진 (DE)에 의해 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugMessageEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자를 위한 정보  
 DE 사용자 응답을 필요로 하는 Visual Studio에는 메시지를 보내는이 인터페이스를 구현 합니다. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 해당이 인터페이스와 같은 개체에 대해 인터페이스를 구현 해야 합니다. SDM 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  
  
 이 인터페이스의 구현에는 Visual Studio의 호출에 통신 해야 [{1>responsemanager](../../../extensibility/debugger/reference/idebugmessageevent2-setresponse.md) 는 DE에 있습니다. 예를 들어 스레드를 처리 하는 등의 메시지에 게시 된 메시지와이 작업을 수행할 수 있습니다 또는이 인터페이스를 구현 하는 개체 수는 DE에 대 한 참조로 전달 된 응답으로는 DE를 콜백할 `IDebugMessageEvent2::SetResponse`합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 DE을 만들어 응답이 필요한 사용자에 게 메시지를 표시 하려면이 이벤트 개체를 보냅니다. 이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 되 면 SDM에서 제공 되는 콜백 함수입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugMessageEvent2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)|표시할 메시지를 가져옵니다.|  
|[{1>responsemanager](../../../extensibility/debugger/reference/idebugmessageevent2-setresponse.md)|메시지 상자에서 있는 경우 응답을 설정 합니다.|  
  
## <a name="remarks"></a>주의  
 DE 특정 메시지에 대 한 사용자의 특정 응답 해야 하는 경우이 인터페이스를 사용 합니다. 예를 들어 경우 쿼리는 DE "액세스 거부" 메시지는 원격으로 프로그램에 연결 하려고 시도한 후,는 DE이 특정 메시지를 보냅니다에서 Visual Studio는 `IDebugMessageEvent2` 메시지 상자 스타일 지정 된 이벤트 `MB_RETRYCANCEL`합니다. 이 다시 시도 하거나 연결 작업을 취소할 수 있습니다.  
  
 DE이이 메시지는 Win32 함수의 규칙에 따라 처리 하는 하는 방법을 지정 `MessageBox` (참조 [AfxMessageBox](http://msdn.microsoft.com/Library/d66d0328-cdcc-48f6-96a4-badf089099c8) 대 한 자세한 내용은).  
  
 사용 하는 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md) 사용자의 응답을 하지 않아도 되는 Visual Studio에 메시지를 보내는 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)
