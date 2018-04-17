---
title: IDebugObject2::GetBackingFieldForProperty | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject2::GetBackingFieldForProperty
helpviewer_keywords:
- IDebugObject2::GetBackingFieldForProperty method
ms.assetid: e72c6338-5573-4fad-8075-f3ade3435424
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7729f55c93274796d3c81f280618653b873bc40b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugobject2getbackingfieldforproperty"></a>IDebugObject2::GetBackingFieldForProperty
필드 또는 변수를 가져옵니다 (있는 경우)는이 개체에 의해 표현 되는 속성 백업 될 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetBackingFieldForProperty(  
   IDebugObject2** ppObject  
);  
```  
  
```csharp  
int GetBackingFieldForProperty(  
   out IDebugObject2 ppObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppObject`  
 [out] [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) 지원 필드를 설명 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) get 사용 하 여 메서드 즉, 관리 코드 클래스 속성을 나타내는 개체 및/또는 set 접근자입니다. 이러한 속성에는 일반적으로 속성에 의해 조작 하는 값을 포함 하는 변수가 필요 합니다. 이 변수를 지원 필드 라고 합니다. 개체의 지원 필드가 없는 경우 다음 있는지 확인 null 값을 반환할: 일부 호출자가 반환 값에 주의 수 있지만에 null 값이 반환 하는 경우 참조 대신 보이는지 `ppObject`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)