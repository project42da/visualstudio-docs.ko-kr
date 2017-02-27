---
title: "IDebugObject::IsEqual | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugObject::IsEqual"
helpviewer_keywords: 
  - "IDebugObject::IsEqual 메서드"
ms.assetid: 4b76e663-ef2e-41ff-9be1-bf26d666a34a
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugObject::IsEqual
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 개체와 개체를 비교합니다.  
  
## 구문  
  
```cpp#  
HRESULT IsEqual(   
   IDebugObject* pObject,  
   BOOL*         pfIsEqual  
);  
```  
  
```c#  
int IsEqual(  
   IDebugObject pObject,  
   out int      pfIsEqual  
);  
```  
  
#### 매개 변수  
 `pObject`  
 \[in\] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 을 비교 하 여 개체를 나타내는 개체입니다.  
  
 `pfIsEqual`  
 \[out\] 0이 아닌 반환 \(`TRUE`\)는 개체의 값이 같은; 경우 그렇지 않은 경우 0을 반환 \(`FALSE`\).  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 주소가 표시 되는 값의이 방법을 비교할 수 있습니다 일반적으로 `pObject` 매개 변수를 사용 하 고이 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체입니다. 주소가 같으면 다음 개체 같다고 취급 될 수 있습니다.  
  
## 참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)