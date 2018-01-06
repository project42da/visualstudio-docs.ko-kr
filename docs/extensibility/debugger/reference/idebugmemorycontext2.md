---
title: IDebugMemoryContext2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMemoryContext2
helpviewer_keywords: IDebugMemoryContext2 interface
ms.assetid: 3a544c8b-11dc-46bb-8549-261e4ac5bbc4
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d3219c5618fbb59438ec6d7ad0aa54e2fbbb1213
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmemorycontext2"></a>IDebugMemoryContext2
이 인터페이스는 디버깅 중인 프로그램을 실행 하는 컴퓨터의 주소 공간에서의 위치를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugMemoryContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE)는 메모리의 주소를 나타내는 데이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 에 대 한 호출 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) 또는 [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md) 이 인터페이스를 반환 합니다. 호출 또한 [추가](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md) 및 [Subtract](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md) 적절 한 산술 연산을 적용 된 후이 인터페이스의 새 복사본을 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugMemoryContext2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugmemorycontext2-getname.md)|이 컨텍스트에 대 한 사용자 표시 이름을 가져옵니다.|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)|이 컨텍스트를 설명 하는 정보를 가져옵니다.|  
|[추가](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md)|새 컨텍스트를 만들 현재 컨텍스트 주소에 지정된 된 값을 추가 합니다.|  
|[Subtract](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md)|새 컨텍스트를 만들 현재 컨텍스트 주소에서 지정 된 값을 뺍니다.|  
|[Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)|두 가지 컨텍스트 방식에서으로 표시 하는 비교 플래그를 비교 합니다.|  
  
## <a name="remarks"></a>설명  
 Visual Studio의 **메모리** 창 호출 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) 얻으려고는 `IDebugMemoryContext2` 메모리 주소에 사용 되는 계산된 된 식을 포함 하는 인터페이스입니다. 이 컨텍스트에 전달 되어 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md) 및 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md) 읽기 또는 쓰기 주소를 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)   
 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)   
 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)