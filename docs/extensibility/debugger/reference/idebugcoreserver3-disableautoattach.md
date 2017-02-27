---
title: "IDebugCoreServer3::DisableAutoAttach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCoreServer3::DisableAutoAttach"
helpviewer_keywords: 
  - "IDebugCoreServer3::DisableAutoAttach"
ms.assetid: 9d860a20-c154-4df4-ba15-636e0fcd42bf
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# IDebugCoreServer3::DisableAutoAttach
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 서버와 연결 된 모든 디버그 엔진에 대 한 자동 연결을 사용 하지 않습니다.  
  
## 구문  
  
```cpp#  
HRESULT DisableAutoAttach(  
   void  
);  
```  
  
```c#  
int DisableAutoAttach();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)