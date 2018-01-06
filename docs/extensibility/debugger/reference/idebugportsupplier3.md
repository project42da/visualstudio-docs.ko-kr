---
title: IDebugPortSupplier3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortSupplier3
helpviewer_keywords: IDebugPortSupplier3 interface
ms.assetid: e458cd02-2370-4435-8953-17d7a60ce152
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f0e1c5c252e0674ee3de8371080e298f42de2112
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportsupplier3"></a>IDebugPortSupplier3
이 인터페이스는 호출자가 포트 공급자의 디버거 호출 사이의 (디스크에 작성) 하 여 포트를 유지 하 고 다음 유지 된 포트 목록을 받을 수 있는지 여부를 확인할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPortSupplier3 : IDebugPortSupplier2  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 사용자 지정 포트 공급자 지속 또는 포트 정보를 디스크에 저장을 지원 하기 위해이 인터페이스를 구현 합니다. 와 같은 개체에 대해이 인터페이스를 구현 해야 합니다는 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 [QueryInterface](/cpp/atl/queryinterface) 에 `IDebugPortSupplier2` 인터페이스가이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 상속 된 메서드 외에 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) 인터페이스,이 인터페이스에서는 다음을 지원 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[CanPersistPorts](../../../extensibility/debugger/reference/idebugportsupplier3-canpersistports.md)|여부 포트 공급자 유지할 수 포트 (디스크에 작성) 하 여 디버거 호출 사이의 반환 합니다.|  
|[EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md)|열거 하는이 포트 공급 업체에 의해 디스크에 기록 된 모든 포트를 통해 사용할 수 있는 개체를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 여러 호출 간에 포트 공급자 포트를 유지할 수, 하는 경우에이 인터페이스를 구현 해야 합니다. 포트는 포트 공급자를 인스턴스화할 이며 포트 공급자 소멸 될 때 디스크에 쓸 때 로드 해야 합니다.  
  
 디버그 엔진 일반적으로 포트 공급자 상호 작용 하지 않습니다 있으며,이 인터페이스에 대 한가 사용 되지 않지만 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)