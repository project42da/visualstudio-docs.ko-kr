---
title: IDebugCoreServer3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCoreServer3
helpviewer_keywords:
- IDebugCoreServer3 interface
ms.assetid: 51f5f41b-a5a4-4df0-a703-41f3d1811d7f
caps.latest.revision: 8
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
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: caa07706e507bb6f6b8aa84404eab5e67579be5b
ms.lasthandoff: 04/05/2017

---
# <a name="idebugcoreserver3"></a>IDebugCoreServer3
이 인터페이스는 프로세스에서 실행 중인 서버에 대 한 정보에 액세스할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugCoreServer3 : IDebugCoreServer2  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 Visual Studio는이 인터페이스를 구현합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수는 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) 인터페이스입니다. 에 대 한 호출 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md) 이 인터페이스를 반환할 수도 있습니다. 이 인터페이스는 (로컬 또는 원격) 서버에 프로그램을 시작 하려면 사용자 지정 포트 공급 업체별 가장 자주 사용 됩니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 메서드 외에도 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetServerName](../../../extensibility/debugger/reference/idebugcoreserver3-getservername.md)|서버 이름을 검색합니다.|  
|[GetServerFriendlyName](../../../extensibility/debugger/reference/idebugcoreserver3-getserverfriendlyname.md)|서버 이름의 친숙 한 버전을 검색합니다.|  
|[EnableAutoAttach](../../../extensibility/debugger/reference/idebugcoreserver3-enableautoattach.md)|자동으로 해당 프로세스를 시작 하는 경우 프로세스에 연결 하는 특정 디버그 엔진에 알려 줍니다.|  
|[DiagnoseWebDebuggingError](../../../extensibility/debugger/reference/idebugcoreserver3-diagnosewebdebuggingerror.md)|자동 연결 실패 하는 경우 특정 오류 코드를 검색 합니다.|  
|[CreateInstanceInServer](../../../extensibility/debugger/reference/idebugcoreserver3-createinstanceinserver.md)|서버에서 디버그 엔진의 인스턴스를 만듭니다.|  
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugcoreserver3-queryislocal.md)|호출자와 동일한 컴퓨터에 서버 인지를 나타내는 플래그를 검색 합니다.|  
|[GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)|서버와 통신 하는 데 사용 되는 프로토콜을 나타내는 값을 검색 합니다.|  
|[DisableAutoAttach](../../../extensibility/debugger/reference/idebugcoreserver3-disableautoattach.md)|이 서버에서 검색 하는 모든 디버그 엔진에 대 한 설정을 자동 연결 하는 모든 사용 하지 않습니다.|  
  
## <a name="remarks"></a>설명  
 사용자 지정 포트 공급자 받는 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) 인터페이스에 대 한 호출에 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md)합니다. `IDebugCoreServer3` 해당 인터페이스에서 인터페이스를 가져올 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)
