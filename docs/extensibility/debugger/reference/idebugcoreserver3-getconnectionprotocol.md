---
title: "IDebugCoreServer3::GetConnectionProtocol | Microsoft Docs"
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
  - "IDebugCoreServer3::GetConnectionProtocol"
helpviewer_keywords: 
  - "IDebugCoreServer3::GetConnectionProtocol"
ms.assetid: 368ced5b-c5d9-4090-a5b4-26ff400d1a55
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugCoreServer3::GetConnectionProtocol
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

서버와 디버그 패키지 간의 통신에 사용 되는 프로토콜을 나타내는 값을 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetConnectionProtocol(  
   CONNECTION_PROTOCOL* pProtocol  
);  
```  
  
```c#  
int GetConnectionProtocol(  
   CONNECTION_PROTOCOL[] pProtocol  
);  
```  
  
#### 매개 변수  
 `pProtocol`  
 \[out\] 값 중 하나를 반환 합니다는 [CONNECTION\_PROTOCOL](../../../extensibility/debugger/reference/connection-protocol.md) 열거형입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [CONNECTION\_PROTOCOL](../../../extensibility/debugger/reference/connection-protocol.md)