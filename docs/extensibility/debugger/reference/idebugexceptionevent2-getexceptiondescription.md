---
title: "IDebugExceptionEvent2::GetExceptionDescription | Microsoft Docs"
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
  - "IDebugExceptionEvent2::GetExceptionDescription"
helpviewer_keywords: 
  - "IDebugExceptionEvent2::GetExceptionDescription"
ms.assetid: d07d458f-5729-47e4-9b77-1bd59c61a75a
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugExceptionEvent2::GetExceptionDescription
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

예외를 표시할 수 있는 설명을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetExceptionDescription(   
   BSTR* pbstrDescription  
);  
```  
  
```c#  
int GetExceptionDescription(   
   out string pbstrDescription  
);  
```  
  
#### 매개 변수  
 `pbstrDescription`  
 \[out\] 예외를 표시할 수 있는 설명을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드에서 반환 되는 문자열은 일반적으로 예외 이름을 이며 표시 됩니다 있는  **출력** 예외가 발생할 때 창.  
  
## 참고 항목  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)