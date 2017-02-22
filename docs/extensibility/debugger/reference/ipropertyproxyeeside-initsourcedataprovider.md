---
title: "IPropertyProxyEESide::InitSourceDataProvider | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IPropertyProxyEESide::InitSourceDataProvider"
helpviewer_keywords: 
  - "IPropertyProxyEESide::InitSourceDataProvider"
ms.assetid: 5156f593-5052-4e3a-9d02-081916fb342d
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IPropertyProxyEESide::InitSourceDataProvider
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 개체에 대 한 원본 데이터를 초기화 하 고 초기 데이터가 들어 있는 개체를 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT InitSourceDataProvider(  
   IEEDataStorage** dataOut  
);  
```  
  
```c#  
int InitSourceDataProvider(  
   out IEEDataStorage dataOut  
);  
```  
  
#### 매개 변수  
 `dataOut`  
 \[out\] 반환 된 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 개체  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 돌아올 수 있도록 개체를 초기화 해야 하는 무엇이 든 하지는 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) 인터페이스는 개체의 데이터에 있습니다.  이 개체의 데이터를 보거나 형식을 시각화 도우미에서 허용 하는 경우 변경할 수 있습니다.  
  
## 참고 항목  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)