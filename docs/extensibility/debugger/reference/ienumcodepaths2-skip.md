---
title: "IEnumCodePaths2::Skip | Microsoft Docs"
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
  - "IEnumCodePaths2::Skip"
helpviewer_keywords: 
  - "IEnumCodePaths2::Skip"
ms.assetid: 356472d8-68b2-4b7e-b5f0-1f16d4ee80af
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumCodePaths2::Skip
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

지정한 수의 요소를 건너뜁니다.  
  
## 구문  
  
```cpp#  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```c#  
int Skip(  
   uint celt  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 건너뛸 요소의 수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 경우 `celt` 나머지 요소; 개수 보다 큽니다 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 경우 `celt` 숫자 보다 큰 값을 지정 합니다. 나머지 요소를 열거형을 끝으로 설정 됩니다 및 `S_FALSE` 이 반환 됩니다.  
  
## 참고 항목  
 [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)