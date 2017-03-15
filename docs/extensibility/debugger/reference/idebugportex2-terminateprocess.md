---
title: "IDebugPortEx2::TerminateProcess | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortEx2::TerminateProcess"
helpviewer_keywords: 
  - "IDebugPortEx2::TerminateProcess"
ms.assetid: bf8fa94c-6d9d-4e4f-ac08-3b44ba5ace68
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPortEx2::TerminateProcess
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로세스를 종료합니다.  
  
## 구문  
  
```cpp#  
HRESULT TerminateProcess(   
   IDebugProcess2* pPortProcess  
);  
```  
  
```c#  
int TerminateProcess(   
   IDebugProcess2 pPortProcess  
);  
```  
  
#### 매개 변수  
 `pPortProcess`  
 \[in\] [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 를 종료 하는 프로세스를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)