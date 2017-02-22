---
title: "IEnumDebugCustomAttributes::Skip | Microsoft Docs"
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
  - "IEnumCustomAttributes::Skip"
helpviewer_keywords: 
  - "IEnumDebugCustomAttributes::Skip"
ms.assetid: 54c72e23-cd4c-4746-935c-abea8057dd1b
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugCustomAttributes::Skip
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용자 지정 특성은 열거 시퀀스에서 지정한 개수의 건너뜁니다.  
  
## 구문  
  
```cpp#  
HRESULT Skip (   
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
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)