---
title: IDebugObject::IsEqual | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject::IsEqual
helpviewer_keywords:
- IDebugObject::IsEqual method
ms.assetid: 4b76e663-ef2e-41ff-9be1-bf26d666a34a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cccce3a530aa1871e093ce5a4ab9187f1ce9d4b1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugobjectisequal"></a>IDebugObject::IsEqual
이 개체와 개체를 비교합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsEqual(   
   IDebugObject* pObject,  
   BOOL*         pfIsEqual  
);  
```  
  
```csharp  
int IsEqual(  
   IDebugObject pObject,  
   out int      pfIsEqual  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pObject`  
 [in] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 비교할 개체를 나타내는 개체입니다.  
  
 `pfIsEqual`  
 [out] 0이 아닌 반환 (`TRUE`) 개체의 값은 같고, 그렇지 않으면 0이 반환 (`FALSE`).  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드 주소를 나타내는 값을 비교할 수는 일반적으로 `pObject` 매개 변수 및이 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체; 주소가 같으면 개체 취급 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)