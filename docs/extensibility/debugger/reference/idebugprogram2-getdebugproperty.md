---
title: IDebugProgram2::GetDebugProperty | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::GetDebugProperty
helpviewer_keywords:
- IDebugProgram2::GetDebugProperty
ms.assetid: d194224e-f0e6-46ab-85d4-9e2639e28946
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 49c83cb4ca1dccbdf1e28d545bdcaa711e3241a6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogram2getdebugproperty"></a>IDebugProgram2::GetDebugProperty
프로그램의 속성을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDebugProperty(   
   IDebugProperty2** ppProperty  
);  
```  
  
```csharp  
int GetDebugProperty(   
   out IDebugProperty2 ppProperty  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppProperty`  
 [out] 반환 된 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 프로그램의 속성을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드에 의해 반환 되는 속성은 프로그램 관련이 있습니다. 둘 이상의 속성을 반환 하는 프로그램에 필요한 경우 그런 다음 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 이 메서드에서 반환 된 개체는 추가 속성 및 호출의 컨테이너는 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 메서드가 반환 되는 모든 속성 목록입니다.  
  
 모든 개수와 유형의 추가 속성을 통해 기술 할 수 있는 프로그램 노출 될 수 있습니다는 `IDebugProperty2` 인터페이스입니다. IDE는 일반 속성 브라우저 사용자 인터페이스를 통해 추가 프로그램 속성을 표시할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)