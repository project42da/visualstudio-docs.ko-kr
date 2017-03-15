---
title: "IEnumDebugFields::GetCount | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugFields::GetCount"
helpviewer_keywords: 
  - "IEnumDebugFields::GetCount 메서드"
ms.assetid: 3f471b40-4db3-49f7-b504-58b2476eef74
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IEnumDebugFields::GetCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드 열거형의 요소 수를 반환합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetCount(  
   [out] ULONG* pcelt  
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
 이 메서드는 다음, 클론, 건너뛰기 및 다시 구현 해야 하는 지정 관습 COM 열거형 인터페이스의 일부가 아닙니다.  
  
## 참고 항목  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)