---
title: "IEnumDebugObjects::Clone | Microsoft Docs"
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
  - "IEnumDebugObjects::Clone"
helpviewer_keywords: 
  - "IEnumDebugObjects::Clone 메서드"
ms.assetid: cb7df109-d29a-4218-b900-6809091459dd
caps.latest.revision: 5
caps.handback.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugObjects::Clone
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 복사본을 현재 열거를 별도 개체로 반환 됩니다.  
  
## 구문  
  
```cpp#  
HRESULT Clone(  
   IEnumDebugObjects** ppEnum  
);  
```  
  
```c#  
int Clone(  
   out IEnumDebugObjects ppEnum  
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
 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)