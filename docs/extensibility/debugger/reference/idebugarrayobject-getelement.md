---
title: "IDebugArrayObject::GetElement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugArrayObject::GetElement"
helpviewer_keywords: 
  - "IDebugArrayObject::GetElement 메서드"
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugArrayObject::GetElement
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

배열 요소를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetElement(   
   DWORD          dwIndex,  
   IDebugObject** ppElement  
);  
```  
  
```c#  
int GetElement(  
   [In] uint dwIndex,   
   out IDebugObject ppElement  
);  
```  
  
#### 매개 변수  
 `dwIndex`  
 \[in\] 요소의 인덱스입니다.  
  
 `ppElement`  
 \[out\] 반환 된 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 인터페이스의 요소를 나타냅니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 Array 개체의 다차원 경우에이 방법을 모든 요소를 array 개체의 1 차원 배열로 볼 수 있습니다.  예를 들어, 배열의 지정 된 `myarray[3][2][6]` 하는 `dwIndex` 매개 변수에 20 요소에서이 메서드는 반환 됩니다 `myarray[1][1][2]`, 하는 `dwIndex` 매개 변수 21의 요소를 반환 `myarray[1][1][3]`.  사용은 [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) 메서드는 배열에 있는 요소의 총 수를 확인할 수 있습니다.  
  
## 참고 항목  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)