---
title: IDebugCoreServer2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugCoreServer2
helpviewer_keywords:
- IDebugCoreServer2 interface
ms.assetid: 9c47d0a6-9eb1-464e-bd44-fa2b552d4d36
caps.latest.revision: 14
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 31961d62c2ef7a253a16a5384dfa6b5e69209a97
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcoreserver2"></a>IDebugCoreServer2
이 인터페이스는 표시 하 고 네트워크에서 컴퓨터에 서버에서 정보를 얻을 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugCoreServer2 : IUknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 Visual Studio는 서버를 나타내는 데이 인터페이스를 구현 합니다. Visual Studio의 각 인스턴스는이 인터페이스의 인스턴스를 만듭니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 사용자 지정 포트 공급자에 대 한 호출에서이 인터페이스에 부여 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md)합니다.  
  
 디버그 엔진에 대 한 호출을 통해 간접적으로이 인터페이스를 가져올 수 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md) (반환 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)에서 파생 된 인터페이스 `IDebugCoreServer2`).  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugCoreServer2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetMachineInfo](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineinfo.md)|이름 및 컴퓨터의 특성을 가져옵니다.|  
|[GetMachineName](../../../extensibility/debugger/reference/idebugcoreserver2-getmachinename.md)|컴퓨터의 이름을 가져옵니다.|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)|컴퓨터에 존재 하는 포트 공급자를 가져옵니다.|  
|[GetPort](../../../extensibility/debugger/reference/idebugcoreserver2-getport.md)|컴퓨터에 이미 할당 된 포트를 가져옵니다.|  
|[EnumPorts](../../../extensibility/debugger/reference/idebugcoreserver2-enumports.md)|컴퓨터에서 모든 포트에 대 한 열거자를 만듭니다.|  
|[EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)|컴퓨터에서 포트의 모든 공급 업체에 대 한 열거자를 만듭니다.|  
|[GetMachineUtilities_V7](../../../extensibility/debugger/reference/idebugcoreserver2-getmachineutilities-v7.md)|컴퓨터를 위한 시스템 유틸리티를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 또한이 인터페이스는 네트워크에 있는 컴퓨터에서 실행 중인 프로세스를 찾아볼 수 Visual Studio에서 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)   
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)