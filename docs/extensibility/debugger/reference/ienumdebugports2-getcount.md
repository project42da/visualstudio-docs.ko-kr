---
title: "IEnumDebugPorts2::GetCount | Microsoft Docs"
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
  - "IEnumDebugPorts2::GetCount"
helpviewer_keywords: 
  - "IEnumDebugPorts2::GetCount"
ms.assetid: d714455c-e4fc-48dc-a6d4-7e8b5d7c1bce
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugPorts2::GetCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

열거형의 요소 수를 반환합니다.  
  
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
 이 메서드를 사용할 수 없습니다. 지정만 일반적인 COM 열거형 인터페이스는 `Next`, `Clone`, `Skip`, 및 `Reset` 메서드 구현 해야.  
  
## 참고 항목  
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)