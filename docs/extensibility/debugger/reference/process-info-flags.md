---
title: "PROCESS_INFO_FLAGS | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROCESS_INFO_FLAGS"
helpviewer_keywords: 
  - "PROCESS_INFO_FLAGS 열거형"
ms.assetid: 696951ce-701a-40c2-ac8c-b897f3aae6e2
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# PROCESS_INFO_FLAGS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

설명 또는 프로세스의 속성을 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_PROCESS_INFO_FLAGS {   
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,  
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,  
   PIFLAG_PROCESS_STOPPED   = 0x00000004,  
   PIFLAG_PROCESS_RUNNING   = 0x00000008,  
};  
typedef DWORD PROCESS_INFO_FLAGS;  
```  
  
```c#  
enum enum_PROCESS_INFO_FLAGS {   
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,  
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,  
   PIFLAG_PROCESS_STOPPED   = 0x00000004,  
   PIFLAG_PROCESS_RUNNING   = 0x00000008,  
};  
```  
  
## Members  
 PIFLAG\_SYSTEM\_PROCESS  
 프로세스는 시스템 프로세스입니다.  
  
 PIFLAG\_DEBUGGER\_ATTACHED  
 프로세스는 디버거를 통해 디버깅 중인 나타냅니다.  것은 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 디버거, 또는 일부 다른 디버거 WinDbg 예를 들어 있을 수 있습니다.  
  
 PIFLAG\_PROCESS\_STOPPED  
 프로세스를 중지를 나타냅니다.  유효한 경우에만 `PIFLAG_DEBUGGER_ATTACHED` 도 지정 됩니다.  사용할 수 있는 [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)] 이상입니다.  
  
 PIFLAG\_PROCESS\_RUNNING  
 프로세스 실행을 나타냅니다.  유효한 경우에만 `PIFLAG_DEBUGGER_ATTACHED` 도 지정 됩니다.  사용할 수 있는 [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)] 이상입니다.  
  
## 설명  
 사용 되는 `Flags` 의 멤버는 [PROCESS\_INFO](../../../extensibility/debugger/reference/process-info.md) 구조.  
  
 이러한 플래그의 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROCESS\_INFO](../../../extensibility/debugger/reference/process-info.md)