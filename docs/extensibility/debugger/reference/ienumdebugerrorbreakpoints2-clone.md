---
title: "IEnumDebugErrorBreakpoints2::Clone | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugErrorBreakpoints2::Clone"
helpviewer_keywords: 
  - "IEnumDebugErrorBreakpoints2::Clone"
ms.assetid: f6fb4985-8dd6-4a9b-98e0-15dbc64cc9ec
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IEnumDebugErrorBreakpoints2::Clone
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

현재 열거를 별도 개체로 복사본을 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT Clone(  
   IEnumDebugErrorBreakpoints2** ppEnum  
);  
```  
  
```c#  
int Clone(  
   out IEnumDebugErrorBreakpoints2 ppEnum  
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
 [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)