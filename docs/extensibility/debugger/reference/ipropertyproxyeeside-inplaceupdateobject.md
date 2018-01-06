---
title: IPropertyProxyEESide::InPlaceUpdateObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IPropertyProxyEESide::InPlaceUpdateObject
helpviewer_keywords: IPropertyProxyEESide::InPlaceUpdateObject
ms.assetid: abf89411-1853-4f23-b244-d5e0afa197b1
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dbfecf353dcdb64e6f576a14413923083e7103eb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ipropertyproxyeesideinplaceupdateobject"></a>IPropertyProxyEESide::InPlaceUpdateObject
지정 된 데이터 개체와 개체의 데이터를 업데이트 하 고 개체의 새 데이터를 나타내는 새 데이터 개체를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT InPlaceUpdateObject(  
   [in] IEEDataStorage*   dataIn,  
   [out] IEEDataStorage** dataOut  
);  
```  
  
```csharp  
int InPlaceUpdateObject(  
   IEEDataStorage     dataIn,  
   out IEEDataStorage dataOut  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dataIn`  
 [in] [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 새 데이터를 포함 하는 개체입니다.  
  
 `dataOut`  
 [out] 새 반환 `IEEDataStorage` 대체 데이터를 포함 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 실제로 개체의 데이터를 업데이트합니다. 반환 된 데이터 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 개체는 들어오는 데이터와 동일 하지 않아도 `IEEDataStorage` 개체가 아니라는 반환 된 개체 속성의 현재 값을 반영 해야 합니다.  
  
 들어오는 데이터 개체 일반적으로 EE에서 구현 되지 않습니다. 그러나이 메서드에서 반환 된 개체는 항상 EE 구현 수 있도록 하는 EE에서 구현 된 `IEEDataStorage` 어떤 클래스가 필요한 경우에 인터페이스입니다.  
  
 [CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md) 메서드는 들어오는 데이터 개체에 따라 데이터 개체를 만들지만 속성의 원래 데이터는 영향을 주지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)