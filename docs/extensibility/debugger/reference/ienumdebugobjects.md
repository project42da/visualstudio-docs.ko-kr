---
title: IEnumDebugObjects | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumDebugObjects
helpviewer_keywords:
- IEnumDebugObjects interface
ms.assetid: 0950364c-6c8a-4b6c-ba37-c6aa359fa72c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 99c6c7a98074753e9ee7e1364adb35e1cdba9700
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ienumdebugobjects"></a>IEnumDebugObjects
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 이 인터페이스를 구현 하는 개체의 컬렉션을 나타냅니다는 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEnumDebugObjects : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 구현 하는 개체의 집합을 제공 하려면이 인터페이스를 구현 하는 식 계산기는 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 인터페이스입니다. 이 하지 있어 표준 COM 열거형은 [GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md) 메서드.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md) 이 인터페이스를 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)|다음 검색 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 열거에 있는 개체입니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugobjects-skip.md)|지정 된 항목 수를 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugobjects-reset.md)|열거형의 첫 번째 항목을 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugobjects-clone.md)|현재 열거형의 복사본을 검색 합니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md)|열거형에 있는 항목의 수를 검색 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스에는 배열에 있는 개체의 집합 전체를 열거 하는 디버그 엔진을 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)