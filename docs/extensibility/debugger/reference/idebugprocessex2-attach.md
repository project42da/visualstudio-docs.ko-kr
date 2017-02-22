---
title: "IDebugProcessEx2::Attach | Microsoft Docs"
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
  - "IDebugProcessEx2::Attach"
helpviewer_keywords: 
  - "IDebugProcessEx2::Attach 메서드"
ms.assetid: f3334ed7-39bf-4d02-a338-36f567b9b287
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProcessEx2::Attach
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 프로세스 세션 프로세스는 현재 디버깅 하 알려 줍니다.  
  
## 구문  
  
```cpp#  
HRESULT Attach(   
   IDebugSession2* pSession  
);  
```  
  
```c#  
int Attach(  
   IDebugSession2 pSession  
);  
```  
  
#### 매개 변수  
 `pSession`  
 \[in\] 이 프로세스에 연결 하는 세션에 고유 하 게 식별 하는 값입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 인터페이스에 전달 된 `pSession` 만 쿠키를 연결 하는이 과정에; 디버그 세션 관리자를 고유 하 게 식별 하는 값으로 처리 하는 것 메서드에 제공 된 인터페이스의 기능입니다.  
  
## 참고 항목  
 [IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)