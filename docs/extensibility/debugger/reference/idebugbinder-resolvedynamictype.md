---
title: IDebugBinder::ResolveDynamicType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBinder::ResolveDynamicType
helpviewer_keywords: IDebugBinder::ResolveDynamicType method
ms.assetid: 2c36ef92-5b44-4cfd-988e-54a2e5a6710c
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3dcd4b946e5b8c2d4cd7c3d77c77140e66699cef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugbinderresolvedynamictype"></a>IDebugBinder::ResolveDynamicType
이 메서드는 정확한 형식의 변수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ResolveDynamicType (  
   IDebugDynamicField *pDynamic,  
   IDebugField       **ppResolved  
);  
```  
  
```csharp  
int ResolveDynamicType(  
   IDebugDynamicField pDynamic,   
   out IDebugField    ppResolved  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pDynamic`  
 [in] [IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md) 변수의 형식을 나타내는입니다.  
  
 `ppResolved`  
 [out] 반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 변수의 형식에 대 한 특정 정보를 제공 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md)