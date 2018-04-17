---
title: IDebugDefaultPort2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDefaultPort2
helpviewer_keywords:
- IDebugDefaultPort2 interface
ms.assetid: 7b3452af-9a96-4c4c-9946-4339b72d3d7b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c6d131ab24cc57af1846f89b61afa2d89ae2cacb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugdefaultport2"></a>IDebugDefaultPort2
이 인터페이스는 포트의 서버 및 알림 기능에 액세스 하는 여러 가지 방법을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugDefaultPort2 : IDebugPort2  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 Visual Studio는 프로그램에 액세스 하기 위한 디버그 포트를 나타내는 데이 인터페이스를 구현 합니다. 또한 사용자 지정 포트 공급자 수 원격 디버깅을 처리 하는 경우이 인터페이스를 구현 해야 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 에 대 한 메서드를 인수는 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md) 인터페이스는이 인터페이스를 제공 합니다. 호출 [QueryInterface](/cpp/atl/queryinterface) 에 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 인터페이스 또한이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 에 정의 된 메서드 외에도 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md),이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md)|이 포트에서 포트 알림 인터페이스를 가져옵니다.|  
|[GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)|이 포트를 호스팅하는 서버에 인터페이스를 가져옵니다.|  
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugdefaultport2-queryislocal.md)|이 포트는 로컬 컴퓨터에서 실행 되 고 있는지 확인 합니다.|  
  
## <a name="remarks"></a>설명  
 이름 "`IDebugDefaultPort2`" 잘못 된 명칭을 줄이려면 상당한은 기본 포트를 나타내지 않습니다. "IDebugPort3" 호출 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)