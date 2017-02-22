---
title: "PROCESS_INFO_FIELDS | Microsoft Docs"
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
  - "PROCESS_INFO_FIELDS"
helpviewer_keywords: 
  - "PROCESS_INFO_FIELDS 열거형"
ms.assetid: 0d9cc345-3d3a-44d8-ae15-a67acb97a828
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# PROCESS_INFO_FIELDS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로세스를 검색할 수 있는 정보의 종류를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_PROCESS_INFO_FIELDS {   
   PIF_FILE_NAME             = 0x00000001,  
   PIF_BASE_NAME             = 0x00000002,  
   PIF_TITLE                 = 0x00000004,  
   PIF_PROCESS_ID            = 0x00000008,  
   PIF_SESSION_ID            = 0x00000010,  
   PIF_ATTACHED_SESSION_NAME = 0x00000020,  
   PIF_CREATION_TIME         = 0x00000040,  
   PIF_FLAGS                 = 0x00000080,  
   PIF_ALL                   = 0x000000ff  
};  
typedef DWORD PROCESS_INFO_FIELDS;  
```  
  
```c#  
public enum enum_PROCESS_INFO_FIELDS {   
   PIF_FILE_NAME             = 0x00000001,  
   PIF_BASE_NAME             = 0x00000002,  
   PIF_TITLE                 = 0x00000004,  
   PIF_PROCESS_ID            = 0x00000008,  
   PIF_SESSION_ID            = 0x00000010,  
   PIF_ATTACHED_SESSION_NAME = 0x00000020,  
   PIF_CREATION_TIME         = 0x00000040,  
   PIF_FLAGS                 = 0x00000080,  
   PIF_ALL                   = 0x000000ff  
};  
```  
  
## Members  
 PIF\_FILE\_NAME  
 초기화\/사용의 `bstrFileName` 필드는 [PROCESS\_INFO](../../../extensibility/debugger/reference/process-info.md) 구조입니다.  
  
 PIF\_BASE\_NAME  
 초기화\/사용의 `bstrBaseName` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF\_TITLE  
 초기화\/사용의 `bstrTitle` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF\_PROCESS\_ID  
 초기화\/사용의 `ProcessId` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF\_SESSION\_ID  
 초기화\/사용의 `dwSessionId` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF\_ATTACHED\_SESSION\_NAME  
 초기화\/사용의 `bstrAttachedSessionName` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF\_CREATION\_TIME  
 초기화\/사용의 `CreationTime` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF\_FLAGS  
 초기화\/사용의 `Flags` 필드는 `PROCESS_INFO` 구조입니다.  
  
 PIF\_ALL  
 모든 필드를 채웁니다.  
  
## 설명  
 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) 필드의 나타내도록 메서드는 [PROCESS\_INFO](../../../extensibility/debugger/reference/process-info.md) 구조에 있는 초기화.  
  
 사용 `Fields` 필드는 `PROCESS_INFO` 구조 필드 사용 되는 및 잘못 된 것을 나타냅니다.  
  
 이러한 플래그의 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROCESS\_INFO](../../../extensibility/debugger/reference/process-info.md)