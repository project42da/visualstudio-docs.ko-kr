---
title: "IEEVisualizerService::GetPropertyProxy | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEEVisualizerService::GetPropertyProxy"
helpviewer_keywords: 
  - "IEEVisualizerService::GetPropertyProxy 메서드"
ms.assetid: 748750f4-76e7-4580-9da2-afba07681b37
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IEEVisualizerService::GetPropertyProxy
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 속성이 개체의 프록시를 반환합니다.  
  
## 구문  
  
```cpp  
HRESULT GetPropertyProxy(  
   DWORD                  dwID,  
   IPropertyProxyEESide** proxy  
);  
```  
  
```c#  
int GetPropertyProxy(  
   uint                     dwID,  
   out IPropertyProxyEESide proxy  
);  
```  
  
#### 매개 변수  
 `dwID`  
 \[in\] 검색에 프록시 속성의 ID입니다.  
  
 `proxy`  
 \[out\] 원하는 프록시 구현에 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) 인터페이스입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md)형식을 시각화 도우미에 대 한 요청이 지원의 일환으로이 메서드에 전달합니다.  
  
## 참고 항목  
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md)