---
title: "IPropertyProxyProvider::GetPropertyProxy | Microsoft Docs"
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
  - "IPropertyProxyProvider::GetPropertyProxy"
helpviewer_keywords: 
  - "IPropertyProxyProvider::GetPropertyProxy"
ms.assetid: 3ebb7515-5bfe-48f4-9b8d-721b8f664eb6
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# IPropertyProxyProvider::GetPropertyProxy
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

지정한 프록시 ID에 대 한 속성 프록시 인터페이스를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetPropertyProxy(  
   DWORD                  dwID,  
   IPropertyProxyEESide** proxy  
);  
```  
  
```c#  
int GetPropertyProxy(  
   uint                     dwID,  
   out IPropertyProxyEESide proxy  
);  
```  
  
#### 매개 변수  
 `dwID`  
 \[in\] 원하는 속성 프록시의 ID입니다.  
  
 `proxy`  
 \[out\] 반환 된 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 외부 형식 시각화를 지원 하기 위해이 방법을 일반적으로 호출을 전달의 [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md) 메서드가 있습니다.  참조 하십시오 [시각화 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md) Ieevisualizerservice를 얻는 방법에 대 한 자세한 합니다.  
  
## 참고 항목  
 [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)   
 [시각화 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md)