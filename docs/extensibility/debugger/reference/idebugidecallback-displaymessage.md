---
title: "IDebugIDECallback::DisplayMessage | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugIDECallback::DisplayMessage"
ms.assetid: c19b48ee-b370-4fce-91fe-f82bf1e63179
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugIDECallback::DisplayMessage
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버거의 출력 창에는 지정 된 메시지 문자열을 보냅니다.  
  
## 구문  
  
```cpp#  
HRESULT DisplayMessage (  
   LPCOLESTR szMessage  
);  
```  
  
```c#  
int DisplayMessage (  
   string szMessage  
);  
```  
  
#### 매개 변수  
 `szMessage`  
 \[in\] 디버거의 출력 창에 표시 하는 메시지 문자열입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugIDECallback](../../../extensibility/debugger/reference/idebugidecallback.md)