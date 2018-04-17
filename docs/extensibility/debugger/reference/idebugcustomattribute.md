---
title: IDebugCustomAttribute | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCustomAttribute
helpviewer_keywords:
- IDebugCustomAttribute interface
ms.assetid: c5ae41e9-00b9-4cca-871d-b8de9ef390d1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f0d7497f5fcda3b871c5a1ad57cf04767617bdab
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugcustomattribute"></a>IDebugCustomAttribute
이 인터페이스 사용자 지정 특성을 나타내고 이름, 부모 및 특성의 클래스 형식을 제공할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugCustomAttribute : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 기호 공급자 기호와 관련 된 사용자 지정 특성을 지원 하기 위해이 인터페이스를 구현 합니다. 일반적으로 자체의 개체에 구현 됩니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 에 대 한 호출 [다음](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md) 이 인터페이스를 반환 합니다. 에 대 한 호출에서 [EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md) 메서드가 반환 되는 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md) 인터페이스입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugCustomAttribute`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetParentField](../../../extensibility/debugger/reference/idebugcustomattribute-getparentfield.md)|현재 특성과 연결 된 필드를 가져옵니다.|  
|[GetAttributeTypeField](../../../extensibility/debugger/reference/idebugcustomattribute-getattributetypefield.md)|사용자 지정 특성 클래스 유형을 가져옵니다.|  
|[GetName](../../../extensibility/debugger/reference/idebugcustomattribute-getname.md)|사용자 지정 특성의 이름을 가져옵니다.|  
|[GetAttributeBytes](../../../extensibility/debugger/reference/idebugcustomattribute-getattributebytes.md)|바이트의 blob으로 특성 정보를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 사용자 지정 특성에는 특정 클래스 또는 메서드를 연관 된 사용자 지정 메타 데이터를 제공 하는 C#에 대 한 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)