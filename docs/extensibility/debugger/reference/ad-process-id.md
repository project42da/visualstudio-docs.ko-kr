---
title: "AD_PROCESS_ID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AD_PROCESS_ID"
helpviewer_keywords: 
  - "AD_PROCESS_ID 공용 구조체"
ms.assetid: 4cb40d12-2e92-4f09-83f4-689928bd65b3
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# AD_PROCESS_ID
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로세스 ID는 시스템 ID 또는 GUID를 지정 합니다.  
  
## 구문  
  
```cpp#  
typedef struct _AD_PROCESS_ID {  
   AD_PROCESS_ID_TYPE ProcessIdType;  
   union {  
      DWORD dwProcessId;   
      GUID  guidProcessId;   
      DWORD dwUnused;   
   } ProcessId;  
} AD_PROCESS_ID;  
```  
  
```c#  
public struct AD_PROCESS_ID {  
   AD_PROCESS_ID_TYPE ProcessIdType;  
   DWORD              dwProcessId;   
   GUID               guidProcessId;   
   DWORD              dwUnused;   
};  
```  
  
## Members  
 `ProcessIdType`  
 값은 [AD\_PROCESS\_ID\_TYPE](../../../extensibility/debugger/reference/ad-process-id-type.md) 해석 하는 방법을 지정 하는 열거형의 `ProcessId` union \(또는 관리 코드에서 액세스할 수 있는 구조체의 멤버에 대 한\).  
  
 dwProcessId  
 값은 시스템에서 프로세스 ID입니다.  
  
 guidProcessId  
 프로세스 ID를 GUID로.  
  
 dwUnused  
 안쪽 여백입니다.  
  
## 설명  
 이 구조는 다음 방법으로 전달 됩니다.  
  
-   [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)  
  
-   [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)  
  
-   [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)  
  
-   [GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)  
  
 다음 방법 중에서 반환 됩니다.  
  
-   [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)  
  
-   [GetHostId](../../../extensibility/debugger/reference/idebugprogramhost2-gethostid.md)  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)   
 [PROCESS\_INFO](../../../extensibility/debugger/reference/process-info.md)   
 [AD\_PROCESS\_ID\_TYPE](../../../extensibility/debugger/reference/ad-process-id-type.md)   
 [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)   
 [GetHostId](../../../extensibility/debugger/reference/idebugprogramhost2-gethostid.md)   
 [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)   
 [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)   
 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)