---
title: IDebugManagedObject::GetManagedObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugManagedObject::GetManagedObject
helpviewer_keywords: IDebugManagedObject::GetManagedObject method
ms.assetid: 6abe1402-6aad-41e6-8ec1-ae12d5945992
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cedcd5801d37256bcb419f4b4e6fb5317f0aedbf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugmanagedobjectgetmanagedobject"></a>IDebugManagedObject::GetManagedObject
관리 되는 개체를 나타내는 인터페이스를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetManagedObject(   
   IUnknown** ppManagedObject  
);  
```  
  
```cpp  
int GetManagedObject(  
   out object ppManagedObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppManagedObject`  
 [out] 관리 되는 개체를 나타내는 인터페이스를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드에서 반환 된 인터페이스의 메서드를 호출할 수 있도록 하는 관리 되는 클래스에 의해 구현 된 인터페이스에 대해 쿼리할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)