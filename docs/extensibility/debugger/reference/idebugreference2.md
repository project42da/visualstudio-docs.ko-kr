---
title: IDebugReference2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugReference2
helpviewer_keywords: IDebugReference2 interface
ms.assetid: 3cfed312-f532-4bce-84a5-1677c14567d7
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 27e880dbf5b602c1bd0b98c6ce5ccc2fdf88e37a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugreference2"></a>IDebugReference2
이 인터페이스는 스택 프레임 속성 또는 일부 다른 속성에 대 한 참조를 나타냅니다.  
  
> [!NOTE]
>  `IDebugReference2`나중에 사용할 수 있도록 하 고 모든 해당 메서드를 반환 해야 하기 위해 예약 되어 `E_NOTIMPL`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugReference2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 특정 유형의 값에 대 한 참조를 나타내는 데이 인터페이스를 구현 합니다. 예를 들어, 값에는 식 계산, 메모리 또는 레지스터와 해당 값의 목록 표시에 사용 되는 메모리 내 컨텍스트에 결과로 숫자 값을 수 있습니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 [GetReference](../../../extensibility/debugger/reference/idebugproperty2-getreference.md) 이 인터페이스를 가져올 수 있습니다. [GetParent](../../../extensibility/debugger/reference/idebugreference2-getparent.md) 및 [GetDerivedMostReference](../../../extensibility/debugger/reference/idebugreference2-getderivedmostreference.md) 또한이 인터페이스를 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugReference2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)|가져옵니다는 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) 이 참조를 설명 하는 구조입니다.|  
|[SetValueAsString](../../../extensibility/debugger/reference/idebugreference2-setvalueasstring.md)|문자열에서이 참조의 값을 설정 합니다.|  
|[SetValueAsReference](../../../extensibility/debugger/reference/idebugreference2-setvalueasreference.md)|다른 참조에서이 참조의 값을 설정 합니다.|  
|[EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)|이 참조의 자식을 열거합니다.|  
|[GetParent](../../../extensibility/debugger/reference/idebugreference2-getparent.md)|이 참조의 부모를 가져옵니다.|  
|[GetDerivedMostReference](../../../extensibility/debugger/reference/idebugreference2-getderivedmostreference.md)|이 참조의 가장 많이 파생 된 참조를 가져옵니다.|  
|[GetMemoryBytes](../../../extensibility/debugger/reference/idebugreference2-getmemorybytes.md)|이 참조에서 참조 하는 메모리 바이트 수를 가져옵니다.|  
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)|이 참조에 대 한 메모리 컨텍스트를 가져옵니다.|  
|[GetSize](../../../extensibility/debugger/reference/idebugreference2-getsize.md)|이 참조를 바이트 단위로 크기를 가져옵니다.|  
|[SetReferenceType](../../../extensibility/debugger/reference/idebugreference2-setreferencetype.md)|이 참조 형식을 설정합니다.|  
|[Compare](../../../extensibility/debugger/reference/idebugreference2-compare.md)|이 참조 된 다른 비교합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  하지만 이러한 "property"를 사용이 하는 클래스의 멤버 변수 해당 의미와 혼동 해서는 안는 `IDebugReference2` 이 엔터티를 나타낼 수 있습니다.  
  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 는 속성을 나타내는 반면 `IDebugReference2` 일반적으로 디버깅 중인 프로그램의 개체에 대 한 참조는 속성에 대 한 참조를 나타냅니다.  
  
 속성과 대 한 참조 간의 주요 차이점은 참조는 명명 되지 않은 인스턴스를 참조 하는 동안 속성 개체의 명명된 된 인스턴스를 참조 합니다. 속성으로 프로그램의 힙에 있는 개체를 참조할 수 있습니다는 예를 들어 `"a.b"`합니다. 다른 속성으로 동일한 개체를 참조할 수 있습니다 `"c.d"`합니다. 사용 하려면이 속성을 참조 하는 방법은 `"a.b"` 또는 `"c.d"` 범위에 속해 있습니다. 동일한이 개체에 대 한 참조는 이름이 없습니다. 해당 개체에 대 한 메모리는 유효한 개체를 참조할 수 있습니다.  
  
 `IDebugProperty2` 인터페이스 이름, 형식 및 주소를 사용 하 여 값으로 생각할 수 있습니다. `IDebugReference2`다른, 전달, 형식과 주소도 생각할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetReference](../../../extensibility/debugger/reference/idebugproperty2-getreference.md)