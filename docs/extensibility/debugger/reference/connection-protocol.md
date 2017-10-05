---
title: CONNECTION_PROTOCOL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CONNECTION_PROTOCOL
helpviewer_keywords:
- CONNECTION_PROTOCOL enumeration
ms.assetid: 99df5865-8b36-486d-9f4c-d10ae2bc688a
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 2be5678704e9a5899c4ce7f5caba8cec1d8a21e6
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# CONNECTION_PROTOCOL
디버그 하는 서버와 디버그 패키지 (DE) 간의 통신에 사용 되는 프로토콜을 나타냅니다.  
  
## 구문  
  
```cpp  
typedef enum tagCONNECTION_PROTOCOL {  
   CONNECTION_NONE    = 0,  
   CONNECTION_UNKNOWN = 1,  
   CONNECTION_LOCAL   = 2,  
   CONNECTION_PIPE    = 3,  
   CONNECTION_TCPIP   = 4,  
   CONNECTION_HTTP    = 5,  
   CONNECTION_OTHER   = 6  
} CONNECTION_PROTOCOL;  
```  
  
```csharp  
public enum CONNECTION_PROTOCOL {  
   CONNECTION_NONE    = 0,  
   CONNECTION_UNKNOWN = 1,  
   CONNECTION_LOCAL   = 2,  
   CONNECTION_PIPE    = 3,  
   CONNECTION_TCPIP   = 4,  
   CONNECTION_HTTP    = 5,  
   CONNECTION_OTHER   = 6  
};  
```  
  
#### 매개 변수  
 CONNECTION_NONE  
 서버를 연결 하지 했습니다.  
  
 CONNECTION_UNKNOWN  
 연결 된 내용이 있지만 알 수 없는 형식입니다.  
  
 CONNECTION_LOCAL  
 로컬 서버입니다.  
  
 CONNECTION_PIPE  
 명명 된 파이프를 통해 연결이 있습니다.  
  
 CONNECTION_TCPIP  
 연결에서 TCP/IP를 사용 합니다.  
  
 CONNECTION_HTTP  
 연결 (웹 서버)를 통해 HTTP를 사용합니다.  
  
 CONNECTION_OTHER  
 다른 유형의 연결을 설정한 (이 값은 현재 사용 되지).  
  
## 설명  
 이러한 값이 반환 된 [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md) 메서드.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)
