---
title: "IDebugProcessSecurity::QueryCanSafelyAttach | Microsoft Docs"
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
  - "IDebugProcessSecurity::QueryCanSafelyAttach"
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
caps.latest.revision: 4
caps.handback.revision: 4
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProcessSecurity::QueryCanSafelyAttach
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 사용자가 안전 하지 않은 프로세스에 연결 하기 전에 경고를 표시 하려면 포트 공급자가 있습니다.  
  
## 구문  
  
```cpp#  
HRESULT QueryCanSafelyAttach();  
```  
  
```c#  
int QueryCanSafelyAttach();  
```  
  
## 반환 값  
 반환 값은 다음과 같습니다.  
  
-   `S_OK`: 프로세스에 연결 하는 것은 안전 하지 하 고 경고 대화 상자가 표시 됩니다.  
  
-   `S_FALSE`: 첨부 보안 문제가 될 수 및 경고 메시지가 포함 된 대화 상자가 표시 됩니다.  
  
-   `FAILURE`: 프로세스에 연결할 수 없습니다.  
  
## 참고 항목  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)