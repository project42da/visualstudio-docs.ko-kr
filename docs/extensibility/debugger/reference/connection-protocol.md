---
title: "CONNECTION_PROTOCOL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CONNECTION_PROTOCOL"
helpviewer_keywords: 
  - "CONNECTION_PROTOCOL 열거형"
ms.assetid: 99df5865-8b36-486d-9f4c-d10ae2bc688a
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# CONNECTION_PROTOCOL
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 패키지 \(DE\) 디버그 서버 사이의 통신에 사용 되는 프로토콜을 나타냅니다.  
  
## 구문  
  
```cpp  
typedef enum tagCONNECTION_PROTOCOL {  
   CONNECTION_NONE    = 0,  
   CONNECTION_UNKNOWN = 1,  
   CONNECTION_LOCAL   = 2,  
   CONNECTION_PIPE    = 3,  
   CONNECTION_TCPIP   = 4,  
   CONNECTION_HTTP    = 5,  
   CONNECTION_OTHER   = 6  
} CONNECTION_PROTOCOL;  
```  
  
```c#  
public enum CONNECTION_PROTOCOL {  
   CONNECTION_NONE    = 0,  
   CONNECTION_UNKNOWN = 1,  
   CONNECTION_LOCAL   = 2,  
   CONNECTION_PIPE    = 3,  
   CONNECTION_TCPIP   = 4,  
   CONNECTION_HTTP    = 5,  
   CONNECTION_OTHER   = 6  
};  
```  
  
#### 매개 변수  
 CONNECTION\_NONE  
 서버에 연결 되지 않았습니다.  
  
 CONNECTION\_UNKNOWN  
 연결 된 내용이 들어 있지만 알 수 없는 형식입니다.  
  
 CONNECTION\_LOCAL  
 연결 하는 로컬 서버입니다.  
  
 CONNECTION\_PIPE  
 연결을 통해 명명 된 파이프입니다.  
  
 CONNECTION\_TCPIP  
 TCP\/IP 연결을 사용합니다.  
  
 CONNECTION\_HTTP  
 연결 HTTP \(웹 서버를 통해\)를 사용합니다.  
  
 CONNECTION\_OTHER  
 다른 유형의 연결 설정 되었습니다 \(이 값이 현재 사용 되지 않습니다\).  
  
## 설명  
 이러한 값에서 반환 되는 [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md) 메서드.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)