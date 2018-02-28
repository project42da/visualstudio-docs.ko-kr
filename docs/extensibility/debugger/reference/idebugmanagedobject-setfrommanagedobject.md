---
title: IDebugManagedObject::SetFromManagedObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugManagedObject::SetFromManagedObject
helpviewer_keywords:
- IDebugManagedObject::SetFromManagedObject method
ms.assetid: 8700ee8d-2704-4580-bccc-046837a24edd
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: da0526c060175a6e00a7b45a7ef2e347dba0d89e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmanagedobjectsetfrommanagedobject"></a>IDebugManagedObject::SetFromManagedObject
매개 변수로 제공 하는 값 클래스의 인스턴스에서 값 클래스 개체의 인스턴스 값을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetFromManagedObject(   
   IUnknown* pManagedObject  
);  
```  
  
```csharp  
int SetFromManagedObject(  
   object pManagedObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pManagedObject`  
 [in] 새 값을 포함 하는 관리 되는 개체를 나타내는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 로 표현 되는 관리 되는 개체를 변경 하려면이 메서드는는 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md) 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)