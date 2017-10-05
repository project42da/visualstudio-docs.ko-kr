---
title: IDebugBinder::ResolveRuntimeType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBinder::ResolveRuntimeType
helpviewer_keywords:
- IDebugBinder::ResolveRuntimeType method
ms.assetid: 6456ab3e-1c03-4f3c-91f9-16797ab7f5e7
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: be2bbd889fa38645d8c3cd4438786a09819b71f1
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="idebugbinderresolveruntimetype"></a>IDebugBinder::ResolveRuntimeType
이 메서드는 개체의 런타임 형식을 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ResolveRuntimeType(   
   IDebugObject* pObject,  
   IDebugField** ppResolved  
);  
```  
  
```csharp  
int ResolveRuntimeType(  
   IDebugObject     pObject,   
   out IDebugField  ppResolved  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pObject`  
 [in] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 를 해결할 수 있습니다.  
  
 `ppResolved`  
 [out] 개체의 형식을 반환는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 컴파일 타임에 개체의 런타임 형식은 항상 알 수는 없습니다. 예를 들어 다형성을 사용 하는 인수 전달할 수 있습니다는 함수에 단추 클래스 등의 기본 클래스로 합니다. 실제 인수의 라디오 단추 클래스 등의 파생된 클래스를 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
