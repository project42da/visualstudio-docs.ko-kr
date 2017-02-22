---
title: "ATTACH_REASON | Microsoft Docs"
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
  - "ATTACH_REASON"
helpviewer_keywords: 
  - "ATTACH_REASON 열거형"
ms.assetid: 159fb70b-a344-4ba6-9115-b7eaa16e228f
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# ATTACH_REASON
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\) 프로그램 노드에 연결 하는 이유를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
typedef DWORD ATTACH_REASON;  
```  
  
```c#  
public enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
```  
  
## Members  
 ATTACH\_REASON\_AUTO  
 디버그 모드에서 현재 프로세스 이므로 연결 합니다.  
  
 ATTACH\_REASON\_LAUNCH  
 프로세스를 시작한 때문에 연결 합니다.  
  
 ATTACH\_REASON\_USER  
 사용자 요청을 연결 합니다.  
  
## 설명  
 이러한 값을 매개 변수로 사용 되는 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 및 [연결](../../../extensibility/debugger/reference/idebugprogramex2-attach.md) 방법입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [연결](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)