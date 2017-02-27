---
title: "IDebugOutputStringEvent2::GetString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugOutputStringEvent2::GetString"
helpviewer_keywords: 
  - "IDebugOutputStringEvent2::GetString"
ms.assetid: f059f8e0-ad44-49ac-ba90-73576ada5e06
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugOutputStringEvent2::GetString
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

표시할 수 있는 메시지를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetString(   
   BSTR* pbstrString  
);  
```  
  
```c#  
int GetString(   
   out string pbstrString  
);  
```  
  
#### 매개 변수  
 `pbstrString`  
 \[out\] 표시할 수 있는 메시지를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugOutputStringEvent2](../../../extensibility/debugger/reference/idebugoutputstringevent2.md)