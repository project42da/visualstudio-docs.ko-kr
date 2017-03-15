---
title: "IDebugPortEx2::GetPortProcessId | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortEx2::GetPortProcessId"
helpviewer_keywords: 
  - "IDebugPortEx2::GetPortProcessId"
ms.assetid: be85be66-47e6-415f-b0ca-24599aa5f13c
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPortEx2::GetPortProcessId
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트 자체의 프로세스 ID를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetPortProcessId (   
   DWORD* pdwProcessId  
);  
```  
  
```c#  
int GetPortProcessId (   
   out uint pdwProcessId  
);  
```  
  
#### 매개 변수  
 `pdwProcessId`  
 \[out\] 포트 자체의 실제 프로세스 ID를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 W i n 32 런타임에 예를 들어,이 방법을 일반적으로 Win32 함수를 호출 `GetCurrentProcessId` 실제 프로세스 ID를 가져올 수  
  
## 참고 항목  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)