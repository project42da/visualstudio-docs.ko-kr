---
title: "IDebugField::Equal | Microsoft Docs"
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
  - "IDebugField::Equal"
helpviewer_keywords: 
  - "IDebugField::Equal 메서드"
ms.assetid: 75369fe6-ddd3-497d-80d1-2488e6100e9f
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugField::Equal
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는이 필드에 지정 된 필드의 일치 여부를 비교합니다.  
  
## 구문  
  
```cpp#  
HRESULT Equal(   
   IDebugField* pField  
);  
```  
  
```c#  
int Equal(  
   IDebugField pField  
);  
```  
  
#### 매개 변수  
 `pField`  
 \[in\] 이 이와 비교 하는 필드입니다.  
  
## 반환 값  
 반환 된 필드 같은 경우 `S_OK`.  필드를 서로 다른 경우, 반환 `S_FALSE.` 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)