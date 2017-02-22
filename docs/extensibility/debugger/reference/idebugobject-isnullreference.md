---
title: "IDebugObject::IsNullReference | Microsoft Docs"
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
  - "IDebugObject::IsNullReference"
helpviewer_keywords: 
  - "IDebugObject::IsNullReference 메서드"
ms.assetid: 6dbfcdb0-954f-4486-8fac-7ea8d003e3a9
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugObject::IsNullReference
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 개체는 null 참조 인지 여부를 테스트 합니다.  
  
## 구문  
  
```cpp#  
HRESULT IsNullReference(   
   BOOL* pfIsNull  
);  
```  
  
```c#  
int IsNullReference(  
   out int pfIsNull  
);  
```  
  
#### 매개 변수  
 `pfIsNull`  
 \[out\] 0이 아닌 반환 \(`TRUE`\) 경우이 개체는 null 참조입니다. 그렇지 않은 경우 0을 반환 \(`FALSE`\).  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 Null 참조는 빈 개체 또는 개체에 할당 되지 않은 의미 합니다.  
  
## 참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)