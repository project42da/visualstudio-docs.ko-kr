---
title: "PROVIDER_FLAGS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROVIDER_FLAGS"
helpviewer_keywords: 
  - "PROVIDER_FLAGS 열거형"
ms.assetid: 8cbd2312-ed2f-4477-b192-c3f25c6098c3
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# PROVIDER_FLAGS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램 공급자 로부터 얻을 수 원하는 속성을 지정 합니다.  
  
## 구문  
  
```cpp  
enum enum_PROVIDER_FLAGS {  
   PFLAG_NONE                    = 0x00,  
   PFLAG_REMOTE_PORT             = 0x01,  
   PFLAG_DEBUGGEE                = 0x02,  
   PFLAG_ATTACHED_TO_DEBUGGEE    = 0x04,  
   PFLAG_REASON_WATCH            = 0x08,  
   PFLAG_GET_PROGRAM_NODES       = 0x10,  
   PFLAG_GET_IS_DEBUGGER_PRESENT = 0x20  
};  
typedef DWORD PROVIDER_FLAGS;  
```  
  
```c#  
public enum enum_PROVIDER_FLAGS {  
   PFLAG_NONE                    = 0x00,  
   PFLAG_REMOTE_PORT             = 0x01,  
   PFLAG_DEBUGGEE                = 0x02,  
   PFLAG_ATTACHED_TO_DEBUGGEE    = 0x04,  
   PFLAG_REASON_WATCH            = 0x08,  
   PFLAG_GET_PROGRAM_NODES       = 0x10,  
   PFLAG_GET_IS_DEBUGGER_PRESENT = 0x20  
};  
```  
  
## Members  
 PFLAG\_NONE  
 플래그가 지정 되지 않습니다.  
  
 PFLAG\_REMOTE\_PORT  
 호출자가 원하는 다른 컴퓨터에 있는 프로그램의 목록을 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)].  
  
 PFLAG\_DEBUGGEE  
 프로세스의이 인스턴스가 현재 디버깅 중인 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)].  
  
 PFLAG\_ATTACH\_TODEBUGGEE  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]디버깅 중인 프로그램에 연결 되어 있지만 시작 되지 않았습니다.  
  
 PFLAG\_REASON\_WATCH  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]이벤트에 대 한 보고 있습니다.  
  
 PFLAG\_GET\_PROGRAM\_NODES  
 호출자가 려는 `ProgramNodes` 필드는 [PROVIDER\_PROCESS\_DATA](../../../extensibility/debugger/reference/provider-process-data.md) 구조입니다.  
  
 PFLAG\_GET\_IS\_DEBUGGER\_PRESENT  
 호출자가 려는 `fIsTheDebuggerPresent` 필드는 `PROVIDER_PROCESS_DATA` 구조입니다.  
  
## 설명  
 이러한 플래그는 다음 방법으로 전달 됩니다.  
  
-   [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)  
  
-   [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)  
  
-   [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)  
  
 이 값이 비트와 결합 될 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROVIDER\_PROCESS\_DATA](../../../extensibility/debugger/reference/provider-process-data.md)   
 [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)   
 [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)   
 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)