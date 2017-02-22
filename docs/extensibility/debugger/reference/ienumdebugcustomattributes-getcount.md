---
title: "IEnumDebugCustomAttributes::GetCount | Microsoft Docs"
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
  - "IEnumCustomAttributes::GetCount"
helpviewer_keywords: 
  - "IEnumDebugCustomAttributes::GetCount"
ms.assetid: fafe826f-4ebf-4572-b2a3-d5dd2916c12f
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugCustomAttributes::GetCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용자 지정 특성의 수를의 열거자를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetCount(   
   ULONG* pcelt  
);  
```  
  
```c#  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### 매개 변수  
 `pcelt`  
 \[out\] 열거형의 요소 수를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드만을 지정 하는 관습 COM 열거형 인터페이스의 일부가 아닌 `Next`, `Clone`, `Skip`, 및 `Reset` 를 구현 해야 합니다.  
  
## 참고 항목  
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)