---
title: "IDebugArrayObject::GetCount | Microsoft Docs"
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
  - "IDebugArrayObject::GetCount"
helpviewer_keywords: 
  - "IDebugArrayObject::GetCount 메서드"
ms.assetid: 7931f3f7-033c-4bf8-8abd-95183952ebb0
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugArrayObject::GetCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

배열의 요소 수를 가져옵니다.  
  
## 구문  
  
```  
[C++]  
HRESULT GetCount(   
   DWORD* pdwElements  
);  
```  
  
```  
[C#]  
int GetCount(  
   out uint pdwElements  
);  
```  
  
#### 매개 변수  
 `pdwElements`  
 \[out\] 수를 반환합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 Array 개체의 다차원 경우에이 방법을 모든 요소를 array 개체의 1 차원 배열로 볼 수 있습니다.  예를 들어, 배열의 지정 된 `myarray[3][2][6]`, 36에서이 메서드는 반환 합니다는 `pdwElements` 매개 변수.  사용은 [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md) 메서드를 한 번에 개별 요소를 검색할 수 있습니다.  
  
## 참고 항목  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)