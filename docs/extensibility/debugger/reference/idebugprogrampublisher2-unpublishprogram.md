---
title: "IDebugProgramPublisher2::UnpublishProgram | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramPublisher2::UnpublishProgram"
helpviewer_keywords: 
  - "IDebugProgramPublisher2::UnpublishProgram"
ms.assetid: 627e7d38-b2ac-4873-9a40-37ff7f47cd1d
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugProgramPublisher2::UnpublishProgram
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램을 디버깅을 사용할 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT UnpublishProgram(  
   IUnknown* pDebuggeeInterface  
);  
```  
  
```c#  
int UnpublishProgram(  
   object pDebuggeeInterface  
);  
```  
  
#### 매개 변수  
 `pDebuggeeInterface`  
 \[in\] `IUnknown` 인터페이스 프로그램입니다.  에 제공 된 동일한 값입니다 있는 [PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md) 메서드 제거 하는 프로그램을 고유 하 게 식별 하 고 \(즉, 쿠키로 사용\).  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 디버그 엔진 및 디버그 세션 관리자를 프로그램을 사용할 수 있게 하려면 사용 하는 [PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md) 메서드.  
  
## 참고 항목  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md)