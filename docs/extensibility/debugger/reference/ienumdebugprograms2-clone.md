---
title: "IEnumDebugPrograms2::Clone | Microsoft Docs"
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
  - "IEnumDebugPrograms2::Clone"
helpviewer_keywords: 
  - "IEnumDebugPrograms2::Clone"
ms.assetid: 880846c2-39d3-45cd-85c3-ad5409a3710f
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugPrograms2::Clone
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

현재 열거를 별도 개체로 복사본을 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT Clone(  
   IEnumDebugPrograms2** ppEnum  
);  
```  
  
```c#  
int Clone(  
   out IEnumDebugPrograms2 ppEnum  
);  
```  
  
#### 매개 변수  
 `ppEnum`  
 \[out\] 이 열거형에서 별도 개체로 복사본을 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 열거형의 복사본은 원본과 동일한 상태가이 메서드가 호출 될 때 있습니다.  그러나 복사본과 원본의 상태는 별도 및 개별적으로 변경할 수 있습니다.  
  
## 참고 항목  
 [IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md)