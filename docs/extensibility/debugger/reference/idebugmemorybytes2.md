---
title: IDebugMemoryBytes2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMemoryBytes2
helpviewer_keywords: IDebugMemoryBytes2 interface
ms.assetid: d7647575-0e06-4190-88f5-ca40b82209a4
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 80e60a6cfb31532c04963e0347fe95e415d32af4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugmemorybytes2"></a>IDebugMemoryBytes2
이 인터페이스는 메모리의 바이트를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugMemoryBytes2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE)는 메모리의 바이트를 나타내기 위해이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md) 시스템 메모리에 대 한 액세스를 제공 하려면이 인터페이스를 반환 합니다. [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md) 및 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugreference2-getmemorybytes.md) 개체의 바이트에 대 한 액세스를 제공 하려면이 인터페이스를 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugMemoryBytes2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)|지정된 된 위치에서 시작 하는 바이트의 시퀀스를 읽습니다.|  
|[WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)|기록 `dwCount` 부터 바이트 `pStartContext`합니다.|  
|[GetSize](../../../extensibility/debugger/reference/idebugmemorybytes2-getsize.md)|이 인터페이스를 나타내는 메모리를 바이트 단위로 크기를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 속성의 경우는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 배열을 나타내는 인터페이스를 제공는 `IDebugMemoryBytes2` 해당 배열에 값에 액세스 하는 인터페이스입니다.  
  
 Visual Studio의 **메모리 보기** 호출 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md) 검색 하는 `IDebugMemoryBytes2` 시스템 메모리에 액세스 하기 위한 인터페이스입니다. 에 액세스 하는 주소를 가져오는 주소로 메모리 보기에 입력 한 식을 구문 분석 하 고 다음을 사용 하 여 구문 분석 된 식을 평가 하 여 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 가져오려는 `IDebugProperty2` 인터페이스입니다. 에 대 한 호출 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) 반환 된 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 메모리 주소를 설명 하는 합니다. 이 메모리 내 컨텍스트에 전달 되어 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md) 및 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md)   
 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md)   
 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugreference2-getmemorybytes.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)