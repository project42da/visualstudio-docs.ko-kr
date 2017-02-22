---
title: "IDebugArrayObject2::GetBaseIndices | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GetBaseIndices"
  - "IDebugArrayObject2::GetBaseIndices"
ms.assetid: 882951a2-3da0-49bf-8d1e-7daedd13ffe6
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugArrayObject2::GetBaseIndices
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

기본 인덱스 \(경계값\) 차원 배열에 지정 된 각 인덱스에 대 한 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetBaseIndices (  
   DWORD  dwRank,  
   DWORD* dwIndices  
);  
```  
  
```c#  
int GetBaseIndices (  
   uint       dwRank,  
   out uint[] dwIndices  
);  
```  
  
#### 매개 변수  
 `dwRank`  
 \[in\] 배열의 차수 \(등급\)의 수입니다.  
  
 `dwIndices`  
 \[out\] 기본 인덱스 \(경계값\)를 배열 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 예를 들어 '5'를 만든 다음 C\# 코드에서 배열에 대 한이 함수를 반환 합니다.  
  
```  
int[] lengths = { 12 };  
int[] lowerbounds = { 5 };  
Array.CreateInstance(typeof(int), lengths, lowerbounds);  
```  
  
## 참고 항목  
 [IDebugArrayObject2](../../../extensibility/debugger/reference/idebugarrayobject2.md)