---
title: "IDebugArrayObject::GetDimensions | Microsoft Docs"
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
  - "IDebugArrayObject::GetDimensions"
helpviewer_keywords: 
  - "IDebugArrayObject::GetDimensions 메서드"
ms.assetid: 113e0aff-9028-49d6-b104-9fe7be4772d7
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugArrayObject::GetDimensions
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

배열의 차원을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetDimensions(   
   DWORD dwCount,  
   DWORD dwDimensions[]  
);  
```  
  
```c#  
int GetDimensions(  
   [In] uint    dwCount,   
   [Out] uint[] dwDimensions  
);  
```  
  
#### 매개 변수  
 `dwCount`  
 \[in\] 차원 수를 검색 합니다.  
  
 `dwDimensions`  
 \[in, out\] 각 차원의 크기를 사용 하 여 채워지는 배열입니다.  `dwCount`최대 크기를 지정은 `dwDimensions` 배열입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 다차원 배열의 각 차원에 대해 서로 다른 크기를 가질 수 있습니다.  예를 들어, 3 차원 배열을 제공 `myarray[3][2][6]`, 3, 2 및 6에서이 메서드는 반환 합니다는 `dwDimensions` 매개 변수를 순서 대로.  
  
## 참고 항목  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)