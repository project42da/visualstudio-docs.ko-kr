---
title: IDebugAddress2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugAddress2
helpviewer_keywords: IDebugAddress2 interface
ms.assetid: b150e0ed-4ac0-4f8c-9732-4b3e54b9d243
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 13161c2be23d2eec6f1d91fd59fc465cbc59a510
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugaddress2"></a>IDebugAddress2
이 인터페이스를 제공 주소가 개체를 소유 하는 프로세스의 ID에 대 한 액세스는이 인터페이스에서 표시 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugAddress2 : IDebugAddress  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 기호 공급자를 구현 하는 동일한 개체에서이 인터페이스를 구현 하는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다. 이 인터페이스는이 주소와 관련 개체를 소유 하는 프로세스의 ID에 대 한 액세스를 제공 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수는 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서 메서드  
 상속 된 메서드 외에 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetProcessID](../../../extensibility/debugger/reference/idebugaddress2-getprocessid.md)|이 인터페이스를 나타내는 개체를 소유 하는 프로세스의 ID를 검색 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)