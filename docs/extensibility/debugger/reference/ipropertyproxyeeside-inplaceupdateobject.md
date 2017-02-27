---
title: "IPropertyProxyEESide::InPlaceUpdateObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IPropertyProxyEESide::InPlaceUpdateObject"
helpviewer_keywords: 
  - "IPropertyProxyEESide::InPlaceUpdateObject"
ms.assetid: abf89411-1853-4f23-b244-d5e0afa197b1
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IPropertyProxyEESide::InPlaceUpdateObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용 하 여 지정 된 데이터 개체는 개체의 데이터를 업데이트 하 고 새 개체의 데이터를 나타내는 새 데이터 개체를 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT InPlaceUpdateObject(  
   [in] IEEDataStorage*   dataIn,  
   [out] IEEDataStorage** dataOut  
);  
```  
  
```c#  
int InPlaceUpdateObject(  
   IEEDataStorage     dataIn,  
   out IEEDataStorage dataOut  
);  
```  
  
#### 매개 변수  
 `dataIn`  
 \[in\] [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 새 데이터가 들어 있는 개체입니다.  
  
 `dataOut`  
 \[out\] 새 반환 `IEEDataStorage` 대체 데이터를 포함 하는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 실제로 해당 개체의 데이터를 업데이트합니다.  데이터는 반환 된 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 개체에서 들어오는 데이터를 동일 하 게 필요 하지 않은 `IEEDataStorage` 하지만 반환 되는 개체 속성의 현재 값을 반영 합니다.  
  
 들어오는 데이터 개체는 EE에서 일반적으로 구현 되지 않습니다.  그러나이 메서드에 의해 반환 되는 개체 EE 구현할 수 있도록 하는 EE에서 항상 구현 되는 `IEEDataStorage` 인터페이스에 필요한 모든 클래스입니다.  
  
 [CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md) 메서드는 들어오는 데이터 개체를 기준으로 데이터 개체를 만들지만 속성의 원래 데이터는 영향을 주지 않습니다.  
  
## 참고 항목  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)