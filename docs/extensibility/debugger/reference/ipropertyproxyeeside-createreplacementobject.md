---
title: "IPropertyProxyEESide::CreateReplacementObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IPropertyProxyEESide::CreateReplacementObject"
helpviewer_keywords: 
  - "IPropertyProxyEESide::CreateReplacementObject"
ms.assetid: 0cfe79b8-c3f1-48b0-a225-e39dee2c92fe
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IPropertyProxyEESide::CreateReplacementObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

식 계산기 \(EE\)을 특정 데이터 개체의 복사본을 만듭니다.  
  
## 구문  
  
```cpp  
HRESULT CreateReplacementObject(  
   IEEDataStorage*  dataIn,  
   IEEDataStorage** dataOut  
);  
```  
  
```c#  
int CreateReplacementObject(  
   IEEDataStorage     dataIn,  
   out IEEDataStorage dataOut  
);  
```  
  
#### 매개 변수  
 `dataIn`  
 \[in\] [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 복사 될 데이터를 포함 하는 개체입니다.  
  
 `dataOut`  
 \[out\] 새 반환 `IEEDataStorage` 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드에 제공 되는 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 바이트 배열을 나타내는 개체입니다.  이 들어오는 데이터 개체는 EE에서 일반적으로 구현 되지 않습니다.  그러나이 메서드에 의해 반환 되는 개체 EE 구현할 수 있도록 하는 EE에서 항상 구현 되는 `IEEDataStorage` 인터페이스에 필요한 모든 클래스입니다.  
  
 참고 데이터 수신에서 제공 하는 `IEEDataStorage` 개체 같은 데이터에는 나가는 있어야 `IEEDataStorage` 개체입니다.  
  
## 참고 항목  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)