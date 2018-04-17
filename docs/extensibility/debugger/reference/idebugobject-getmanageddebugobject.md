---
title: IDebugObject::GetManagedDebugObject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject::GetManagedDebugObject
helpviewer_keywords:
- IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6c7b416ca9af4279e11cabbbf880a73891059df6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
디버그 엔진의 주소 공간에서 관리 되는 개체의 복사본을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetManagedDebugObject(   
   IDebugManagedObject** ppObject  
);  
```  
  
```csharp  
int GetManagedDebugObject(  
   out IDebugManagedObject ppObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppObject`  
 [out] 반환 된 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md) 새로 만든된 관리 되는 개체를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다. 이 경우 e_fail [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 관리 되는 값 클래스 인스턴스를 나타내지 않습니다.  
  
## <a name="remarks"></a>설명  
 이 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체와 같은 관리 되는 값 클래스 인스턴스를 나타내야 합니다는 `System.Decimal` 인스턴스. 호출의 오버 헤드 로컬 복사본을 사용 함으로써 [평가](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) 제거 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)