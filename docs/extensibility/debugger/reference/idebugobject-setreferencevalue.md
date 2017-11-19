---
title: IDebugObject::SetReferenceValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject::SetReferenceValue
helpviewer_keywords: IDebugObject::SetReferenceValue method
ms.assetid: 08c78a4e-98eb-41cb-8b75-02a6a43d49f7
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1e001e747279ad64c97c500079adc9c4574d1d33
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugobjectsetreferencevalue"></a>IDebugObject::SetReferenceValue
이 개체의 참조 값을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetReferenceValue(   
   IDebugObject* pObject  
);  
```  
  
```csharp  
int SetReferenceValue(  
   [In] IDebugObject pObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pObject`  
 [in] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 새 참조 값을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용 하면이 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체에 지정 된 개체의 값에 대 한 참조는 `pObject` 버리는 이전 참조 매개 변수입니다. 참고가 `IDebugObject` 개체는 이미 참조 형식 이어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)