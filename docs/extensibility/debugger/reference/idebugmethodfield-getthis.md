---
title: IDebugMethodField::GetThis | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::GetThis
helpviewer_keywords:
- IDebugMethodField::GetThis method
ms.assetid: cc235bea-e909-4d8c-ab54-936736c803fc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3cde294ea10a6eedd1046a41686dbfa9f3b47e4e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmethodfieldgetthis"></a>IDebugMethodField::GetThis
가져옵니다는 `this` (`Me` 에 [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]) 메서드를 포함 하는 개체의 포인터입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetThis(   
   IDebugClassField** ppClass  
);  
```  
  
```csharp  
int GetThis(  
   out IDebugClassField ppClass  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppClass`  
 [out] 반환 된 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) "this"이 포인터를 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 개체 지향 언어 즉 일반적으로 클래스는 현재 인스턴스화에 대 한 암시적된 포인터가 있습니다. 로 알려져 `this` C# / c + +와 `Me` 에서 [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)