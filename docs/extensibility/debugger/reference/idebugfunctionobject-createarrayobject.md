---
title: IDebugFunctionObject::CreateArrayObject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugFunctionObject::CreateArrayObject
helpviewer_keywords:
- IDebugFunctionObject::CreateArrayObject method
ms.assetid: a380e53c-15f1-401f-927f-f366eea789e6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 39695d37012f90d7e61c04f64ee1c05f11482373
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugfunctionobjectcreatearrayobject"></a>IDebugFunctionObject::CreateArrayObject
배열 개체를 만듭니다. 이 배열은 개체 인스턴스 값 또는 중 하나가 기본 형식이 포함 될 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateArrayObject(   
   OBJECT_TYPE    ot,  
   IDebugField*   pClassField,  
   DWORD          dwRank,  
   DWORD          dwDims[],  
   DWORD          dwLowBounds[],  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateArrayObject(  
   enum_OBJECT_TYPE ot,   
   IDebugField      pClassField,   
   uint             dwRank,   
   uint[]           dwDims,   
   uint[]           dwLowBounds,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ot`  
 [in] 값을 지정 된 [OBJECT_TYPE](../../../extensibility/debugger/reference/object-type.md) 새 배열 개체의 형식을 나타내는 열거형입니다.  
  
 `pClassField`  
 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인스턴스 값 개체의 배열을 만드는 경우에 개체의 클래스를 나타내는 개체입니다. 기본 개체의 배열을 만드는 경우이 매개 변수는 null 값입니다.  
  
 `dwRank`  
 [in] 순위 또는 배열의 차원 수 있습니다.  
  
 `dwDims`  
 [in] 배열의 각 차원 크기를 지정 합니다.  
  
 `dwLowBounds`  
 [in] 각 차원의 원본 (일반적으로 0 또는 1).  
  
 `ppObject`  
 [out] 반환 된 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 새로 만들어진된 배열을 나타내는 개체입니다. 이 실제로 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 으로 표시 된 함수에는 배열 매개 변수를 나타내는 개체를 만들려면이 메서드를 호출 하는 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)